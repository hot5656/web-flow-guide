# VSCode

*   [Root](../README.md)

### 快捷鍵-	[hot key](https://poychang.github.io/vscode-shortcuts/)
	ctrl-shift-p(or F1) : to command line
	F11 : 全螢幕切換

	ctrl+/ : add comment
	ctrl-p : search file name
	ctl-enter : add next line
	shift-alt-f : align code
	ctl-w : close file
	ctl-2/ctl-3 : open 2nd window/open 3rd window
	ctl-` : open termernal/other windows
	ctl-d : 選擇下一個相同string共同編輯
	alt-(mouse-l) : select 共同編輯
	選擇多行-->shift+alt+(mouse-l) : 多行編輯
	alt+^/alt- : select up/down  
	F1 : select command  
	Ctrl +/- : 字型大小
	Ctrl mouse-left : open reference file
	Ctrl + W 關閉檔案
	Ctrl + K Ctrl + W 關閉所有檔案

### issue
* show manu bar
	F1 -> toggle manu bar
	F11 toogle full screen




### plug package
*	Live Server

*	Live Sass Compiler : sass watch
*	Indent-Rainbow : 縮排採紅色條
* Sass : Indented Sass syntax highlighting, autocomplete & snippets for VSCode
*	Favorites : Favorite directory
*	git history diff  (F1 selectt command)  
	GitHD: View History  
	GitHD: View Branch History  
	GitHD: View Entire History  
	GitHD: View Branch Diff  
	GitHD: View File History  
	GitHD: View Line History  
	GitHD: Input Ref  
* Monokai Dark Soda : 程式編輯佈景  
	檔案 --> 喜好設定 --> 色彩佈景主題 --> Monokai Dark Soda
*	vscode-icons  
	Ctrl+shift+p --> icons: activate VScode icons
*	AutoFileName : auto detect files
* EaseServer : web server  
	ctrl+shift+enter 
* live server : web server	 
*	colorize : look color(scss/sass/color)

***
* Bracket Pair Colorizer : 可以讓不同縮減的括號顯示不同的顏色
* css-auto-prefix : auto insert prefix for css
* Autoprefixer : ctrl-shift-p "Autoprefix css" add prefix for css 
*	Git History : see git log 
*	github extension
*	ESLint/javascript standard style only enable one
	ESLint : 檢查程式碼有沒有整齊(node.js need install "npm install -g eslint")
	javascript standard style : 
		npm install -g eslint
		npm init
		eslin init
			popular-->Airbnb-->javascript
*	perview web server : include live server
		ctr-shift-l : open web side
		ctl-shift-p : open side
*	sublime keymap: plug for sublime key


### configuration setting
Freference-->setting
*	VScode Show Full Path in Title Bar
```
	Window: Title 
		default :
			${dirty}${activeEditorShort}${separator}${rootName}${separator}${appName}
		full fath:
			${activeEditorLong}${separator}${rootName}
```
* show CR/tab/space
```
  	Editor: Render Whitespace
  		none : no show
  		all  : show
```
* 切成中文版  
```
install chinese(Traditional) Languale Pack
ctrl+shift+p --> configure Display Language
   locale 中的 en 改成 zh-TW
從新啟動
```
* liveSassCompile settings autoprefix
```
    "liveSassCompile.settings.autoprefix": [
      "> 1%",
      "last 5 versions",
      "Firefox >= 45",
      "iOS >=8",
      "Safari >=8",
      "ie >= 10"
    ]
```

