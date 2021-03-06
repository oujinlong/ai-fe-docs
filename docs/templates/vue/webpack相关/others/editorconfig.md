# webpack相关
## others

### 2.editorconfig

EditorConfig帮助开发人员在不同的编辑器和IDE之间定义和维护一致的编码样式。EditorConfig项目由用于定义编码样式的**文件格式**和一组**文本编辑器插件**组成，这些插件使编辑器能够读取文件格式并遵循定义的样式。EditorConfig文件易于阅读，并且与版本控制系统配合使用。

EditorConfig即为它的配置文件

	root = true
	告诉EditorConfig插件，这是根文件，不用继续往上查找
	
	[*]
	匹配全部文件
	
	end_of_line = lf
	结尾换行符，可选"lf"、"cr"、"crlf"
	
	insert_final_newline = true
	在文件结尾插入新行

	trim_trailing_whitespace = true
	删除一行中的前后空格
	
	[*.{js,py}]
	匹配js和py结尾的文件
	
	charset = utf-8
	设置字符集
	
	[*.py]
	匹配py结尾的文件
	
	缩进风格，可选"space"、"tab"
	indent_style = space
	
	indent_size = 4
	缩进的空格数

	tab_width = 4
	tab的宽度

