# webpack相关
## build
build 文件夹下共分为3个主要文件

* [build.js](#/templates/vue/webpack相关/build/webpack-build.md) 
* [check-versions.js](#/templates/vue/webpack相关/build/webpack-check-versions.md)
* [utils.js](#/templates/vue/webpacks相关/build/webpack-utils.md)


### 2.check-versions.js
check-versions 用来检测node和npm版本

**引用模块:**
 	
[chalk](https://www.npmjs.com/package/chalk): 控制台字体美化
 	
[semver](https://www.npmjs.com/package/semver): 语义化版本控制规范

[shell](https://www.npmjs.com/package/shell): 执行Unix系统命令

该模块主要核心方法 semver.satisfies(currentVersion, requirementVersion) ,即通过smever进行版本匹配,返回 true 或 false

**工作流程:**

1.获取node当前版本号以及项目package.json所要求最低版本号

		const versionRequirements = [
			  {
			    name: 'node',
			    currentVersion: semver.clean(process.version),
			    versionRequirement: packageConfig.engines.node
			  }
		]
2.获取npm当前版本号以及项目package.json所要求最低版本号

	   	if (shell.which('npm')) {
	   versionRequirements.push({
		    name: 'npm',
		    currentVersion: exec('npm --version'),
		    versionRequirement: packageConfig.engines.npm
		  })
		}
		// #shell.which('npm')
	   //	返回npm绝对路径，否则返回null

   	
3.通过semver.satisfies()方法进行版本匹配
	
	semver.satisfies(mod.currentVersion, mod.versionRequirement
4.提示信息
	
	for (let i = 0; i < warnings.length; i++) {
      const warning = warnings[i]
      console.log('  ' + warning)
    }