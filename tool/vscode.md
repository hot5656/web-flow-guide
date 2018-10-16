# VSCode

*   [Root](../README.md)

### 快捷鍵-	[hot key](../https://poychang.github.io/vscode-shortcuts/)
	ctrl-p : search file name
	ctrl-shift-p : to command line
	ctl-enter : add next line
	shift-alt-f : align code
	ctl-w : close file
	ctl-2/ctl-3 : open 2nd window/open 3rd window
	ctl-` : open termernal/other windows
	ctl-d : 選擇下一個相同string共同編輯
	alt-(mouse-l) : select 共同編輯
	alt+^/alt- : select up/down


### plug package
*	Live Server
*	Git History : see git log 
*	Live Sass Compiler
*	Indent-Rainbow : 縮排採紅色條
* Sass : Indented Sass syntax highlighting, autocomplete & snippets for VSCode
*	Favorites : Favorite directory
* css-auto-prefix : auto insert prefix for css
* Autoprefixer : ctrl-shift-p "Autoprefix css" add prefix for css 

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