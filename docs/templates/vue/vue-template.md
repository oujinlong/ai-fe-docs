#vue-template模板说明

![MacDown logo](http://img3.imgtn.bdimg.com/it/u=1822347002,3097606619&fm=26&gp=0.jpg)

vue 快速建项模版使用说明

[最新版本 v0.1.1](https://github.com/oujinlong/ai-vue-template)

##模板安装
通过 ai-vue 进行安装
###环境要求
* node.js 版本 >= 8.0
* npm 版本 >= 5.0
* vue 版本 >= 2.0 (vue 模版所需)

###安装步骤
	创建项目模版
	ai-fe init
	
	选择 vue-template 模版
	
	选择是否使用 element-ui
	
	输入项目名称
	
	安装完成
	
	运行项目
	cd ${project name} && npm run dev
##项目结构	
		|-- project //webpack 基础配置文件
		    |-- .babelrc 
		    |-- .editorconfig
		    |-- .eslintignore
		    |-- .eslintrc.js
		    |-- .gitignore
		    |-- .postcssrc.js
		    |-- README.md
		    |-- index.html
		    |-- package-lock.json
		    |-- package.json
		    |-- build
		    |   |-- build.js
		    |   |-- check-versions.js
		    |   |-- logo.png
		    |   |-- utils.js
		    |   |-- vue-loader.conf.js
		    |   |-- webpack.base.conf.js
		    |   |-- webpack.dev.conf.js
		    |   |-- webpack.prod.conf.js
		    |-- config
		    |   |-- dev.env.js
		    |   |-- index.js
		    |   |-- prod.env.js
		    |-- docker // 快速 docker 打包模版文件
		    |   |-- Dockerfile
		    |   |-- build.sh
		    |   |-- nginx_prod.conf
		    |   |-- start.sh
		    |   |-- stop.sh
		    |-- src //主要代码文件夹
		    |   |-- App.vue
		    |   |-- main.js //入口文件
		    |   |-- assets // 资源存放文件夹
		    |   |   |-- logo.png
		    |   |   |-- styles // 全局 style
		    |   |       |-- main.scss
		    |   |       |-- base
		    |   |           |-- _variables.scss
		    |   |           |-- components.scss
		    |   |           |-- icons.scss
		    |   |           |-- mixins.scss
		    |   |           |-- transitions.scss
		    |   |-- components
		    |   |   |-- HelloWorld.vue
		    |   |-- libraries // 三方js存放文件夹
		    |   |   |-- plugins
		    |   |   |   |-- authorize.js
		    |   |   |   |-- axios.js
		    |   |   |   |-- index.js
		    |   |   |   |-- nprogress.js
		    |   |   |   |-- title.js
		    |   |   |-- store // 模块化 store 文件夹
		    |   |   |   |-- index.js
		    |   |   |   |-- modules
		    |   |   |       |-- index.js
		    |   |   |-- utils // 工具类文件夹
		    |   |       |-- DataFormat.js
		    |   |       |-- DateTool.js
		    |   |       |-- axios.js
		    |   |       |-- index.js
		    |   |       |-- nprogress.js
		    |   |       |-- storage.js
		    |   |-- router // 路由管理文件夹
		    |   |   |-- index.js
		    |   |   |-- main
		    |   |       |-- index.js
		    |   |-- views //主要视图文件夹
		    |       |-- error // 默认404页面
		    |       |   |-- error.vue
		    |       |-- main 
		    |           |-- style.scss
		    |           |-- temp  //默认模版页面
		    |               |-- temp.vue
		    |               |-- store
		    |               |   |-- index.js
		    |               |-- style
		    |                   |-- temp.scss
		    |-- static
		        |-- .gitkeep
	
	
