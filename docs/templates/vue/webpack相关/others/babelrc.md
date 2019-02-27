# webpack相关
## others

### 1.babelrc

ES6是2015年发布的下一代javascript语言标准，它引入了新的语法和API，使我们编写js代码更加得心应手，比如class，let,for...of promise等等这样的，但是可惜的是这些js新特性只被最新版本的浏览器支持，但是低版本浏览器并不支持，那么低版本浏览器下就需要一个转换工具，把es6代码转换成浏览器能识别的代码，babel就是这样的一个工具。可以理解为 **babel是javascript语法的编译器。**

**1.1babelrc编译器:**

在Babel执行编译的过程中，会从项目的根目录下的 .babelrc文件中读取配置。.babelrc是一个json格式的文件。
在.babelrc配置文件中，主要是对预设(presets) 和 插件(plugins) 进行配置。.babelrc配置文件一般为如下：     

	{
	  "presets": [
	    ["env", {
	      "modules": false,
	      "targets": {
	        "browsers": ["> 1%", "last 2 versions", "not ie <= 8"]
	      }
	    }],
	    "stage-2"
	  ],
	  "plugins": ["transform-vue-jsx", "transform-runtime"]
	}
 
 
 
**1.2 plugins:**

plugins是告诉babel要使用那些插件，这些插件可以控制如何转换代码。
     
[transform-vue-jsx:](https://www.npmjs.com/package/babel-plugin-transform-vue-jsx) 在vue中使用 [jsx语法](https://www.cnblogs.com/zourong/p/6043914.html)

[transform-runtime:](https://www.npmjs.com/package/babel-plugin-transform-runtime)  babel默认只会转译语法，比如箭头函数，spread。全局对象和全局对象的方法，比如Set Map Object.assign，includes默认是不会转译的。需要加polyfill或者transform-runtime。

**1.3 presets:**

presets 创建预设,主要配置如下:

	{
		 "presets": [
			  ["env", options],
			  "stage-2"
		 ]
	}

**options:**

常用options:
	
	{
		  "targets": {
		    "chrome": 52,
		    "browsers": ["last 2 versions", "safari 7"],
		    "node":"6.10"
		  }
		  "modules": false
	}
	
**targets**可以制定兼容浏览器版本，如果设置了browsers，那么就会覆盖targets原本对浏览器的限制配置。

**modules** 放弃使用babel的模块化，使用webpack的模块化,通常配置false

[更多参考](https://babeljs.io/docs/plugins/preset-env/)

	
**stage-2:**
	
不同阶段的转译器之间是包含的关系，preset-stage-0转译器除了包含了preset-stage-1的所有功能还增加了transform-do-expressions插件和transform-function-bind插件，同样preset-stage-1转译器除了包含preset-stage-2的全部功能外还增加了一些额外的功能。	