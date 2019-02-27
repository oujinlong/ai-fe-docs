# webpack相关
## build
build 文件夹下共分为3个主要文件

* [build.js](#/templates/vue/webpack相关/webpack-build.md) 
* [check-versions.js](#/templates/vue/webpack相关/webpack-check-versions.md)
* [utils.js](#/templates/vue/webpacks相关/webpack-utils.md)


### 3.utils.js
utils 是vue **开发环境下** 相关配置文件，主要用来处理css-loader和vue-style-loader
 
**引用模块:**
 	
[path](https://www.npmjs.com/package/path): 路径获取
 	
[check-versions.js](#/templates/vue/webpack/webpack-check-versions.md): npm及依赖所需版本检查,如果低于最低使用版本即退出 build
 	
[ExtractTextPlugin](https://www.npmjs.com/package/extract-text-webpack-plugin): 用来将css提取到单独的css文件中

该模块主要核心方法 generateLoaders的实现

**工作流程:**

1.获取静态资源的相对路径
	
	exports.assetsPath = function (_path) {
	  const assetsSubDirectory = process.env.NODE_ENV === 'production'
	    ? config.build.assetsSubDirectory
	    : config.dev.assetsSubDirectory
	
	  return path.posix.join(assetsSubDirectory, _path)
	}
	// path.join和path.posix.join的区别就是，前者返回的是完整的路径，后者返回的是完整路径的相对根路径

2.导出css相关配置
	
	const cssLoader = {
    loader: 'css-loader',
    options: {
      sourceMap: options.sourceMap
   	 }
  	}
    //	options: {
          minimize: process.env.NODE_ENV === 'production' // 如果是生产环境就压缩代码	
          sourceMap: options.sourceMap

	    }
	    
3.核心方法实现, generateLoaders,用来读取和返回最终调用的loader
	
	 if (options.extract) {
      return ExtractTextPlugin.extract({
        use: loaders,
        fallback: 'vue-style-loader'
      })
    } else {
      return ['vue-style-loader'].concat(loaders)
    }    

4.调用  generateLoaders 方法获得最终返回的 loader

	return {
	    css: generateLoaders(),
	    postcss: generateLoaders(),
	    less: generateLoaders('less'),
	    sass: generateLoaders('sass', { indentedSyntax: true }),
	    scss: generateLoaders('sass'),
	    stylus: generateLoaders('stylus'),
	    styl: generateLoaders('stylus')
  	}