# Sublime 

*   [Root](../README.md)


### 多行編輯

*	滑鼠選中多行，按下Ctrl_Shift_L或Command_Shift_L即可同時編輯這些行
*	滑鼠選中文本，反覆按Ctrl_D 即可繼續向下同時選中下一個相同的文本進
*	鼠標選中文本，按下Alt_F3即可一次性選擇全部的相同文本進行同時編輯
*	Shift+滑鼠右键可以用鼠標進行豎向多行選擇 - ok 
*	Ctrl+滑鼠左键可以手動選擇同時要編輯的多處文本

###  假字
lorem lorem10


### show menu 
Ctl+shift+P  -> (input menu) view:toggle menu


### default project 
edit.sublime-project
	
### set space 2
	1. Preferences --> settings 
	  "tab_size": 2,
	  "detect_indentation": false,
	2. bottom convert indentation to tab

### 單檔分割
File --> new view into file

### some setting 
*	Show all characters (spaces, TABs, CR, LF, etc.)
	```
	Preferences -> Settings - User
	"draw_white_space": "all",
	```

*	install package
	``
	Preferences -> Package Control --> press "install package"
	or
	Ctrl + Shift + P  --> press "install package"
	``

*	Sublime Text 3 Deleting Code when I hit Tab Key
	```
	preferences->key bindings
	{ "keys": ["tab"], "command": "indent" },
	{ "keys": ["shift+tab"], "command": "unindent" }
	```

* open folders 
	File --> open floders

* package  

