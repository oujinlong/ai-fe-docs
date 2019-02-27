# webpack相关
## build
build 文件夹下共分为3个主要文件

* [build.js](#/templates/vue/webpack相关/build/build.md) 
* [check-versions.js](#/templates/vue/webpack相关/build/check-versions.md)
* [utils.js](#/templates/vue/webpack相关/build/utils.md)


### 1.build.js
build.js 是 项目执行 npm run build 后所执行的 node 文件, 即 #npm
run build = #node ./build/build.js,开发者在生产模式下打包所用.

**引用模块:**

[check-versions.js](#/templates/vue/webpack/webpack-check-versions.md): npm及依赖所需版本检查,如果低于最低使用版本即退出 build

[ora](https://www.npmjs.com/package/ora): 命令行loading,success等图标

[rm](https://www.npmjs.com/package/rm):删除某个路径下所有文件夹及文件

[path](https://www.npmjs.com/package/path): 路径获取

[chalk](https://www.npmjs.com/package/chalk): 控制台字体美化

**该模块主要核心方法 webpack(config, error) ,即为当前项目生产模式下打包**

工作流程:

1.检测npm等版本是否符合要求

require('./check-versions')()


2.删除dist文件夹以及assets文件夹

rm(path.join(config.build.assetsRoot, config.build.assetsSubDirectory), err => {})

3.进行webpack打包,重新生成 dist 文件夹

webpack(webpackConfig, (err, stats) => {})

额外配置    配置打包完成后控制台信息输出

process.stdout.write(stats.toString({
colors: true,
modules: false,
children: false, // If you are using ts-loader, setting this to true will make TypeScript errors show up during build.
chunks: false,
chunkModules: false
}) + '\n\n')
