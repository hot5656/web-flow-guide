﻿# HTML record

*   [Root](../README.md)
*   [1. emmet](#a1)
*   [2. lorem 假字](#a2)
*   [3. 版型思考](#a3)
*   [4. variable](#a4)
*   [5. basic struct](#a5)
*   [6. tag](#a6)
*   [7. 模板庫](#a7)
*   [8. HTML head example](#a8)
*   [9. Build a web](#a9)

<h2 id="a1">1. emmet</h2>

```
// 多層 {}:內容
.warp>.menu>ul>li*6>a{hello}

// $=index number
.style${hello}*3

// + 產生同一層
.box+p+h3

// ^ 跳回上一層
div>h3+p^div

// () 可分開
(nav>ul>li*4)+(article>h3>p)

// .:class #:id
.wrap>#header>p.a1.a2

// [] 加入 attribute
img[src="test.jpg" alt="test"]

// {} 內容
P{This is a key}

//@ 起始值
ul>li.item$@5*4

// css 縮寫
m10 : margin: 10px
p10p20p : padding: 10% 20%
fl : float: left
fz16 : font-size: 16px
bd3-s#3  : border: 3s #333333

// html 縮寫
! : HTML5 structure
meta:vp :　<meta name="viewport" content="width=device-width, initial-scale=1.0">
					　<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no"

```

<h2 id="a2">2. lorem 假字</h2>

```
lorem10 : 10字
```


<h2 id="a3">3. 版型思考</h2>

```
(1)背景沒考慮銀幕解析度來去做延伸
(2)元素內的文字沒考慮如果呈現多行時，設計也必須延伸
(3)網頁字型沒考慮到網頁預設字型
(4)hover過後的按鈕樣式並未提供
(5)沒有grid的觀念，每個頁面元素寬度不一
(6)設計的頁面沒辦法程式化
(7)動畫效果過於複雜，無法於時程內完工
- 是否缺功能圖:下拉是選單,功能圖
- 有些圖切透明
- 字型確認
- layout class/structure design
- png copy to one file
```

<h2 id="a4">4. variable</h2>

```
$width: 940px
$body-bg: 
$text-color:pink→預設文字顏色
$font-color:    →強調文字顏色
$link-color:#000→文字連結樣式，多則就再加紹數字
$link-color-hover:#fff→滑鼠拖曳過後的樣式顏色
$font-size:13px→全域字型大小，如一網站有多種就下多種字型
$line-height:1.8→全域行距
$container-width:960px→ 網站整體寬度
$font-style："Helvetica Nueue", Arial, Sans Serif; →全域字型
$line-height: 1.6
```


<h2 id="a5">5. basic struct</h2>

```html
	<div class="wrap">
		<header></header>
		<div class="content"></div>
		<footer></footer>
	</div>
```

<h2 id="a6">6. tag</h2>

```html
<header>：網頁的標頭，通常放置網站標題。
<nav>：網頁的選單、導覽。
<main>：網頁的主要內容。
<aside>：網頁的側欄、附加內容。
<article>：一篇文章內容。
<section>：自訂的區塊，例如數篇摘要組成的空間。
<footer>：網頁的頁尾，通常放置聯絡方式、著作權宣告等等。
<mark>：強調一小塊內容。
<time>：顯示日期時間。

<em>
```


<h2 id="a7">7. 模板庫</h2>

```
// EJS是一個JavaScript模板庫，用來從JSON數據中生成HTML字符串
// Jade 樣板引擎
// Gulp 是一個前端任務管理工具
	編譯 SASS、Coffeescript
	壓縮 .CSS, .JS, 甚至圖檔
	web server with Livereload
	享受自己動手做Task工具的快感
```

<h2 id="a8">8. HTML head example</h2>

[The Open Graph protocol](http://ogp.me/)
```html
// Open Graph protocol
// 過去稱為Facebook Connect API，簡單的說就是，透過Facebook API你將可以取得使用者的個人資料，喜愛偏好
//  現在已有相當多的網站能讀取 Open Graph Protocol
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<!-- Viewport : add set shrink-to-fit=no -->
	<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
	<!-- 什麼版本IE 就用什麼版本的標準模式 -->
	<meta http-equiv="X-UA-Compatible" content="ie=edge">
	<!-- webpage icon -->
	<link rel="icon" href="img/favicon_32.ico" type="image/ico" />
	<!-- Title -->
	<title>甜點電商 - 購物車</title>
	<!-- 網頁標題 -->
	<meta property="og:title" content="甜點電商 - 購物車 "/>
	<!-- 網站描述 -->
	<meta property="og:description" content="最好的甜點"/>
	<!-- 網站名稱 -->
	<meta property="og:site_name" content="甜點電商"/>
	<!-- 網站主要的語系 -->
	<meta property="og:locale" content="zh_TW"/>
	<!-- 其他說明
		網址
		<meta property="og:url" content="網址">
		縮圖網址
		<meta property="og:image" content="要顯示的縮圖網址">
		網頁聲音檔的網址
		<meta property="og:audio" content="網頁聲音檔的網址"/>
		網頁影片網址
		<meta property="og:video" content="網頁影片網址"/>
	-->

	<link rel="stylesheet" href="css/all.css">
	<!-- Material icon	 -->
	<link href="https://fonts.googleapis.com/icon?family=Material+Icons"
  rel="stylesheet">
</head>
<body>
</body>
</html>
```


<h2 id="a9">9. Build a web</h2>

*	build directory 
	```
	twitch_clone - source - img
	                        sass
	```

*	add file (dos)
	```
	./DOS_CMD
	``` 

*	install node.js  

	```
	// ** generate package.json
	npm init
	// ** add autoprefixer for develop
	npm install autoprefixer --save-dev
	// ** add browser-syn for develop
	npm install browser-sync --save-dev
	// ** add gulp package
	npm install gulp --save-dev   
		--> 4.0.0 have issue , chage to 3.9.1
				AssertionError [ERR_ASSERTION]: Task function must be specified
					at Gulp.set [as _setTask] 
	npm install gulp-load-plugins --save-dev
	npm install gulp-plumber --save-dev
	npm install gulp-sourcemaps --save-dev
	npm install gulp-sass --save-dev
	npm install gulp-postcss --save-dev
	npm install gulp-if --save-dev
	npm install gulp-clean-css --save-dev
	npm install gulp-clean --save-dev
	npm install gulp-wait --save-dev
	// ** add gulp-gh-pages for develop
	npm install gulp-gh-pages --save-dev
	// ** add minimist for develop
	npm install minimist --save-dev
	// ** add for layout using ejs format
	// npm install gulp-front-matter --save-dev
	// npm install gulp-layout --save-dev
	// npm install ejs --save-dev
	// ** 
	// ** Babel - he compiler for writing next generation JavaScript.
	npm install babel-loader @babel/core @babel/preset-env --save-dev
	// ** minifi js
	npm install gulp-minify --save-dev
	// ** minify css
	// npm install gulp-clean-css --save-dev
	// ** minify html
	npm install gulp-htmlmin --save-dev
	// ** gulp debug
	npm install gulp-debug  --save-dev
	```
*	add file (basic)

	```
	./.gitignore
		---------
		node_modules
		public
		*.map
		---------
	./gulpfile.js
		---------
		select use ejs or no use ejs
		---------
	./source/sass/all.sass
		---------
		@import init/normalize
		@import init/mixin
		@import init/function
		@import init/variable
		@import init/init
		// ----------------
		@import page/index
		---------
	./source/sass/page/_index.sass
		---------
		---------
	./source/index.html
		---------
		<link rel="stylesheet" href="css/all.css">
		---------
	```
*	copy file(soem sass file)
	```
	./source/sass/init/*
	```

* run gulp
	```
	grup
	```

* add jQuery
	``` css
	// add module
		// install jquery
		npm install jquery --save-dev
		// for third js
		npm install gulp-sequence --save-dev
		npm install gulp-concat --save-dev
	// gulpfile.js
		// add third js module
		const gulpSequence = require('gulp-sequence').use(gulp);

		// add third js module
		gulp.task('vendorJs', () => {
		  return gulp
		    .src([
		      './node_modules/jquery/dist/jquery.slim.min.js'
		    ])
		    .pipe($.concat('vendor.js'))
		    .pipe(gulp.dest('./public/js'));
		});

		// add third js module
		gulp.task('default', ['copy', 'sass', 'vendorJs', 'browserSync', 'watch']);

		// add build for re-build
		// add third js module
		gulp.task('build', gulpSequence('clean', 'copy', 'sass', 'vendorJs', 'sass'));
	// html 
		<script src="js/vendor.js"></script>
		<script src="js/all.js"></script>
	``` 

*	JQuery ajax  
	>	 因放在程式碼中顯示有問題,另外引用列出
	const clientId = 'qvtuq71csrlv5ipxo1ljzgbzqn1okh' ;  
	const limitItem = 20;  
	const apiUrl =  "https://api.twitch.tv/kraken/streams/?client_id=" +
										clientId +
										"&game=League%20of%20Legends&limit=" +
										limitItem ;
	$(document).ready(function(){  
		queryLive(procesLiveInfo) ;  
	});  

	```javascript
	function queryLive(cb) {
		$.ajax({
			dataType: "json",
			url: apiUrl,
			success: function(response){
				console.log(response);
				cb(null, response);
			},
			error: function(err) {
				cb(err);
			}
		});
	}

	function procesLiveInfo(err,data) {
		if (err) {
			console.log(err);
		}
		else {
			const streams =  data.streams;
			const row = $('.row');
			for (let i=0 ; i<streams.length ; i++ ) {
				row.append(getColumn(streams[i]));
			}
		}
	}

	function getColumn(data) {
		return `
		<div class="col">
			<img class="preview" src="${data.preview.large}" alt="">
			<div class="descript">
				<img class="avatar" src="${data.channel.logo}" alt="">
				<div class="introduce">
					<div class="ch-name">${data.channel.status}</div>
					<div class="ch-master">${data.channel.name}</div>
				</div>
			</div>
		</div>
		`;
	}
	```








