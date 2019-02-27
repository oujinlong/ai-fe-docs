# webpack相关
## config

### 1.index.js

index.js 是config的入口文件, 分为 **dev** 和 **build** 配置

**dev配置:**
	
	env: require('./dev.env')
	使用 config/dev.env.js 中定义的编译环境
	
	port:8080
	测试页面的浏览器端口,默认8080
	
	assetsSubDirectory: 'static'
	编译输出的二级目录,默认 static

	assetsPublicPath: '/'
	编译发布的根目录，可配置为资源服务器域名或 CDN 域名
	
    proxyTable: {
      'api': {
        target: 'http://10.1.239.45:28020/',
        target: 'http://127.0.0.1',
        changeOrigin: true,
        pathRewrite: {
          '^/api': '/crm-web'
          '^/api': '/'
        }
      }
    }
    反向代理,可解决跨域问题
    
     cssSourceMap: false
     是否开启 cssSourceMap
     
     autoOpenBrowser: true
     在调试模式下是否在启动时自动打开浏览器
     
     errorOverlay: ture
     是否自动查询错误
     
     notifyOnErrors: true
     是否后通知错误
     
     poll: false
     poll是跟devserver相关的一个配置，webpack为我们提供的devserver是可以监控文件改动的，但在有些情况下却不能工作，我们可以设置一个轮询（poll）来解决
     
     useEslint: true
     是否使用 Eslint
     
     showEslintErrorsInOverlay: false
     是否展示Eslint的错误提示
     
     devtool
     webpack提供的用来方便调试的配置(详情见最下方附表)
     
 
	 cacheBusting
	 一个配合devtool的配置，当给文件名插入新的hash导致清楚缓存时是否生成souce maps，默认在开发环境下为true
	 
 **build配置:**
 
**附:devtool配置表**

![devtool](https://github.com/oujinlong/ai-fe-docs/blob/master/docs/templates/vue/webpack%E7%9B%B8%E5%85%B3/config/devtool.png?raw=true)
  +++ super fast, ++ fast, + pretty fast, o medium, - pretty slow, -- slow
     
 
 
     
     
