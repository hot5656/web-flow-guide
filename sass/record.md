# sass record

*   [Root](../README.md)
*   [1. variable](#a1)
*   [2. install compile](#a2)
*   [3. config.rb modify](#a3)
*   [4. import other scss file](#a4)
*   [5. mixin - 幫助記住css技巧](#a5)
*   [6. RWD](#a6)
*   [7. 加減乘除](#a7)
*   [8. sector標誌](#a8)
*   [9. @extend合併css](#a9)
*   [10. compass](#a10)
*   [10-2. compass appliaction](#a10-2)
*   [11. mixin example](#a11)
*   [12. mixin using](#a12)
*   [13. sass init example](#a13)
*   [14. add web style select](#a14)
*   [15. compass sprite](#a15)

<h2 id="a1">1. variable</h2>

```
// varibale start from $
	$font-stack:    Helvetica, sans-serif;
	$primary-color: #333;

	body {
	  font: 100% $font-stack;
	  color: $primary-color;
	}

// 字串由 #{$name} 取出連接
	$bg: '../images/'
	$icon-style: blue

	.header
		background: url(#{$bg}header.png)

	.icon-#{$icon-style}
		color: $icon-style
```

<h2 id="a2">2. install compile</h2>

```
// install ruby
download rubyinstaller-2.5.1-1-x64.7z

// decompress and add path to .\bin

// install compass
gem install compass

// add sass pjoject (will generate config.rb)
compass create test_project
	=========================
	To import your new stylesheets add the following lines of HTML (or equivalent) to your webpage:
	<head>
	  <link href="/stylesheets/screen.css" media="screen, projection" rel="stylesheet" type="text/css" />
	  <link href="/stylesheets/print.css" media="print" rel="stylesheet" type="text/css" />
	  <!--[if IE]>
	      <link href="/stylesheets/ie.css" media="screen, projection" rel="styleshee
	t" type="text/css" />
	  <![endif]-->
	</head>
	=========================

// watch project 
compass watch test_project
	or
cd test_project
compass watch
```

<h2 id="a3">3. config.rb modify</h2>

```
// sass編譯出來的css不要有註解
將# line_comments = false 前面的#號拿掉就不會產生出註解。

// sass/scss 允許說明輸入中文問題
Encoding.default_external = 'utf-8'

// output_style 編譯出來的CSS碼要用哪種方式編譯出來
expanded = 一般，每行CSS皆會斷行
nested = 有縮進，較好閱讀
compact = 簡潔格式，匯出來的ＣＳＳ檔案大小比上面兩個還小。
compressed = 壓縮過的CSS，所有設定都以一行來進行排列。
```

<h2 id="a4">4. import other scss file</h2>

```
// prepare for import scss(_ start)
		@import 'mixin'
		@import 'reset'
		@import 'layout'
		@import 'module'	//btuuon,form,gtable	

// sass - 實際 code 說明加在後面會有問題
	@import compass/css3  // compass
	@import mixin					// 放置所有Sass全域變數與Mixin
	@import normalize			// normalize file
	@import init					// some modify for normalize
	@import extnd 	// 拿來合併樣式，都放@extend用的檔案
	@import layout	// 共同框架
	@import index		// 首頁
	@import page		// 內頁 
	@import xxx			// 各單元CSS
	@import browser	// if need for RWD
```

<h2 id="a5">5. mixin - 幫助記住css技巧</h2>

```
如果你的程式碼需要帶入多個變數進行運算時那用@mixin
	@mixin hide-text {
		text-indent:110%
		white-space: nowarp;
		overflow: hidden;
  }
  .header h1 {
    	@include hide-text
  }

// sass
$font-size: 13px
@mixin bg($bg-color)
	background: $bg-color
	font-size: $font-size

.header 
	+bg(#fff)
.cotent 
	+bg(red)
// mixin專屬變數也可具有變數預設值
@mixin bg($bgcolor:#000,$width:200px) 
	background: $bgcolor
	width: $width
.header
	+bg
.footer
	+bg(#ff0000,300px)
```


<h2 id="a6">6. RWD</h2>

```
// scss mixin 預設為最小畫面設定
$v-xl:1200px;
$v-lg:992px;
$v-md:768px;
$v-sm:576px;
$v-xm:575px;
@mixin s-xl{
	@media (min-width:v-xl) {
		@content
	}
}
@mixin s-lg{
	@media (min-width:v-lg) {
		@content
	}
}  
@mixin s-md{
	@media (min-width:v-md) {
		@content
	}
} 
@mixin s-sm{
	@media (min-width:v-sm) {
		@content
	}
} 
@mixin s-xm{
	@media (man-width:v-xl) {
		@content
	}
} 

.header {
	width: 100px;
	height:100px;
	@include s-md {
		heigh: auto;
	}
	@include s-xm {
		height: 300px;
	}
}

// sass 預設為最大畫面設定
.box
	width: 500px
	height: 500px
	background: #000000
	a
		color: #ffffff
		font-size: 40px

@media only screen and (max-width: 768px)
	.box
		background: yellow
		a 
			color: red

@media only screen and (max-width: 480px)
	.box 
		background: red
		a 
			color: #ffffff

// sass mixin 預設為最大畫面設定
@mixin breakpoint($point)
	@if $point == pc 
		@media only screen and (max-width: 1024px)
			@content
	@else if $point == pad 
		@media only screen and (max-width: 768px)
			@content	
	@else if $point == mobil 
		@media only screen and (max-width: 320px)
			@content		
	
.box
	width: 500px
	height: 500px
	background: #000000
	+breakpoint(pad)
		background: yellow
	+breakpoint(mobil)
		background: red
	a
		color: #ffffff
		font-size: 40px
		+breakpoint(pad)
			color: red
		+breakpoint(mobil)		
			color: #ffffff
```


<h2 id="a7">7. 加減乘除</h2>

```
$font-size: 16px

.font-big
	font-size: $font-size*1.5

.font-middle
	font-size: $font-size - 2px

.font-small
	font-size: $font-size / 3
```


<h2 id="a8">8. sector標誌</h2>

```
& : 所指的sector
```


<h2 id="a9">9. @extend合併css</h2>

```
如果你的樣式都固定不變的就用@extend
//scss
%clearfix{ 
	& { 
		*zoom: 1; 
	} 
	&:before, 
	&:after { 
		display: table; 
		content: ""; 
	} &:after { 
		clear: both; 
		overflow: hidden; 
	} 
} 

ul{ 
	@extend %clearfix; 
} 
.block { 
	@extend %clearfix; 
}

// sass
%all-h1
	font-size: 20px
	line-height: 1.8
	letter-spacing: 1px

.header h1
	@extend %all-h1
	color: #000000

.content h1
	@extend %all-h1
	color: green
--------------------
.header h1, .content h1 {
  font-size: 20px;
  line-height: 1.8;
  letter-spacing: 1px;
}

.header h1 {
  color: #000000;
}

.content h1 {
  color: green;
}
```

<h2 id="a10">10. compass</h2>

```
// import compass - vscode not support
  @import compass/css3
  	+border-radius(20px) // 會加入前綴詞
  	+opacity(0.8)        // 透明度
  	+box-shadow(red 2px 2px 10px)

// compass mixin
+transition(all 3s cubic-bezier(#{random()}, #{random()}, #{random()}, #{random()}))
+border-radius(50px)
+box-shadow(5px 5px #000)
+box-sizing

// sass function - runy support but vscode not support   
width: image-width("../img/#{$name}.#{$sub}")
height: image-height("../img/#{$name}.#{$sub}")
index($site, cat) : get index position from variable
background: nth($bg, $style) : select array variable value
$box-len: length($box-bg) : variable array length
left: random(1000) - 100 + px : random value between 1 to 1000
cubic-bezier(#{random()}, #{random()}, #{random()}, #{random()}) :　random value between 0 to 1
background: inline-image("../img/logo.png") : 圖檔轉成css(避免過多網頁請求數)

// function for color 
.page
	height: 120px
	background: #ff0000	// 紅色
	background: darken(#ff0000, 10%)	//調暗 10%
	background: lighten(#ff0000, 10%)	//調亮 10%
	background: adjust-hue(#ff0000, 45)	//改變色相 45度
	background: invert(#ff0000) //反色相

```


<h2 id="a10-2">10-2. compass appliaction</h2>

```
// for - font-size
@for $i from 1 through 3
	font-#{$i}
		font-size: $i*2em

// for - color class
$box-bg: blue red pink orange
$box-len: length($box-bg)
.color-total
	color: $box-len
@for $i from 1 through $box-len
	.#{nth($box-bg, $i)}
		color: nth($box-bg, $i)
		background: invert(nth($box-bg, $i))

// for - color ball
$boxes: 100
.box
	margin: 0 auto
	border: 1px solid #000
	height: 1000px
	width: 1000px
	position: relative
	&:hover
		div
			margin-left: 2000px
			// +transition(all 10s) - 不設定即與 div class 設定相同

@for $i from 1 through $boxes
	.for-#{$i}
		color: #000 
		height: 50px
		width: 50px
		+box-shadow(5px 5px #000)
		background: rgb(random(255), random(255),random(255))
		+border-radius(50px)
		position: absolute
		left: random(1000) - 100 + px
		bottom: random(1000) - 100 + px
		+transition(all 3s cubic-bezier(#{random()}, #{random()}, #{random()}, #{random()}))


// inline-image example
.box-test2
	background: inline-image("../img/logo.png")
	width: image-width("../img/logo.png")
	height: image-height("../img/logo.png")
```

<h2 id="a11">11. mixin example</h2>

```
// background image
@mixin bg($name,$sub)
  background-image: url("../img/#{$name}.#{$sub}")
  width: image-width("../img/#{$name}.#{$sub}")
  height: image-height("../img/#{$name}.#{$sub}")
+bg(logo,png)
// background image -2 
@mixin bg($name)
  background-image: url("../img/#{$name}")
  width: image-width("../img/#{$name}")
  height: image-height("../img/#{$name}")
// background image -3 
@mixin bg2($name)
  background-image: image-url($name)
  width: image-width($name)
  height: image-height($name)
+bg('logo.png')
// hide text
@mixin hide-text
  white-space: nowrap	// 空白的處理方法 連續的空白字會縮減為一個空白，不跳行
  text-indent: 100%		// 讓首行縮排 100%
  overflow: hidden
// grid
@mixin grid($width_all, $cloum_number, $cloum_gutter)
  width: ($width_all - $cloum_gutter*($cloum_number - 1))/$cloum_number
  margin-right: $cloum_gutter
  box-sizing: border-box
  &:nth-child(#{$cloum_number}n)
    margin-right: 0
+grid($width, 3, 30px)
// clear fix
@mixin clearfix
  &::after
    display: block
    content: ""
    clear: both
+clearfix
// 圓形
@mixin circle($size, $bg)
  width: $size
  height: $size
  +border-radius($size/2)
  background: $bg
// 三角形　ｄefault 正三角形，type=0.86666 為正三角形
// $direct 箭頭方向
@mixin triangle ($size, $color, $direct,$type:1)
  height: 0
  width: 0
  @if $direct == top 
    border-bottom: ($size*$type) solid $color
    border-left: ($size/2) solid transparent
    border-right: ($size/2) solid transparent
  @else if $direct == right 
    border-left: ($size*$type) solid $color
    border-top: ($size/2) solid transparent
    border-bottom: ($size/2) solid transparent
  @else if $direct == bottom 
    border-top: ($size*$type) solid $color
    border-left: ($size/2) solid transparent
    border-right: ($size/2) solid transparent
  @else if $direct == left 
    border-right: ($size*$type) solid $color
    border-top: ($size/2) solid transparent
    border-bottom: ($size/2) solid transparent
  @else if $direct == right-top
    border-right: $size solid $color
    border-bottom: $size solid transparent
  @else if $direct == left-top
    border-left: $size solid $color
    border-bottom: $size solid transparent
  @else if $direct == right-bottom
    border-right: $size solid $color
    border-top: $size solid transparent
  @else if $direct == left-bottom
    border-left: $size solid $color
    border-top: $size solid transparent
// 矩形
@mixin square($width, $height, $bg, $color)
  box-sizing: border-box
  -webkit-box-sizing: border-box
  -moz-box-sizing: border-box
  width: $width
  height: $height
  background: $bg
  color: $color
```


<h2 id="a12">12. mixin using</h2>

```
// 對話框
.one 
	float: left
	background: white
	height: 300px
	width: 300px
	padding: 30px
	margin-left: 50px
	+border-radius(30px)
	position: relative
	&:before
		+triangle(30px ,white , right)
		position: absolute
		content: ""
		top: 10%
		left: 100%
// 對話框 + 外框
.two 
	float: left
	background: white
	height: 300px
	width: 300px
	padding: 30px
	margin-left: 50px
	+border-radius(30px)
	position: relative
	border: 5px solid #333
	&:before
		+triangle(33px ,#333 , right)
		position: absolute
		content: ""
		top: 30px
		left: 100%
	&:after
		+triangle(20px ,white , right)
		position: absolute
		content: ""
		top: 35px
		left: 100%
// 麵包屑路徑
.crumb
	li
		a
			margin-top: 5px
			position: relative
			float: left
			margin-right: 10px
			line-height: 80px
			padding-left: 70px
			+square(155px, 80px, pink, red)
			font-weight: bold
			font-size: 20px
			&:before
				position: absolute
				left: 100%
				+triangle(80px ,pink , right,0.5)
				content: ''	
				z-index: 20
			&:after
				position: absolute
				left: 0
				+triangle(80px ,#d4f2ff , right,0.5)
				content: ''
				z-index: 10	
			&:hover
				background: blue
				&:before
					border-left-color: blue
		&:first-child
			a
				border-top-left-radius: 10px
				border-bottom-left-radius: 10px
				&:after
					display: none
		&:last-child
			a
				border-top-right-radius: 10px
				border-bottom-right-radius: 10px
				&:before
					display: none
```

<h2 id="a13">13. sass init example</h2>

```sass
html, body, div, span, applet, object, iframe, h1, h2, h3, h4, h5, h6, p, blockquote, pre, a, abbr, acronym, address, big, cite, code, del, dfn, em, img, ins, kbd, q, s, samp, small, strike, strong, sub, sup, tt, var, b, u, i, center, dl, dt, dd, ol, ul, li, fieldset, form, label, legend, table, caption, tbody, tfoot, thead, tr, th, td, article, aside, canvas, details, embed, figure, figcaption, footer, header, hgroup, menu, nav, output, ruby, section, summary, time, mark, audio, video
  margin: 0
  padding: 0
  border: 0
  font: inherit
  vertical-align: baseline

ol, ul
  list-style: none

article, aside, details, figcaption, figure, footer, header, hgroup, main, nav, section, summary
  display: block

audio, canvas, video
  display: inline-block

audio:not([controls])
  display: none
  height: 0

[hidden]
  display: none

a
  &:focus
    outline: thin dotted
  &:active, &:hover
    outline: 0

abbr[title]
  border-bottom: 1px dotted

b, strong
  font-weight: bold

dfn
  font-style: italic

hr
  -moz-box-sizing: content-box
  box-sizing: content-box
  height: 0

mark
  background: #ff0
  color: #000

code, kbd, pre, samp
  font-family: monospace, serif
  font-size: 1em

pre
  white-space: pre-wrap

q
  quotes: "\201C" "\201D" "\2018" "\2019"

small
  font-size: 80%

sub
  font-size: 75%
  line-height: 0
  position: relative
  vertical-align: baseline

sup
  font-size: 75%
  line-height: 0
  position: relative
  vertical-align: baseline
  top: -0.5em

sub
  bottom: -0.25em

img
  max-width: 100%
  height: auto

svg:not(:root)
  overflow: hidden

figure
  margin: 0

fieldset
  border: 1px solid #c0c0c0
  margin: 0 2px
  padding: 0.35em 0.625em 0.75em

legend
  border: 0
  padding: 0

button, input, select, textarea
  font-family: inherit
  font-size: 100%
  margin: 0

button, input
  line-height: normal

button, select
  text-transform: none

button, html input[type="button"]
  -webkit-appearance: button
  cursor: pointer

input
  &[type="reset"], &[type="submit"]
    -webkit-appearance: button
    cursor: pointer

button[disabled], html input[disabled]
  cursor: default

input
  &[type="checkbox"], &[type="radio"]
    box-sizing: border-box
    padding: 0
  &[type="search"]
    -webkit-appearance: textfield
    -moz-box-sizing: content-box
    -webkit-box-sizing: content-box
    box-sizing: content-box
    &::-webkit-search-cancel-button, &::-webkit-search-decoration
      -webkit-appearance: none

button::-moz-focus-inner, input::-moz-focus-inner
  border: 0
  padding: 0

textarea
  overflow: auto
  vertical-align: top

table
  border-collapse: collapse
  border-spacing: 0
.clearfix
  &:before
    content: ""
    display: table
  &:after
    content: ""
    display: table
    clear: both
  zoom: 1
html
  font-family: sans-serif
  line-height: 1
  font-size: 16px

a
  text-decoration: none
  color: black
```



<h2 id="a14">14. add web style selecte</h2>

```
$site: coffee kid cat 
$bg: red yellow green 
$text-color: #fff #ff0000 grey 
$style: index($site, cat)

.color
	background: nth($bg, $style)
	color: nth($text-color, $style)
```


<h2 id="a15">15. compass sprite</h2>

```
// 水平排列
$icon-layout: horizontal 
// 設定間隔
$icon-spacing: 20px
// 轉換檔案(icon目錄放於 img下)
@import icon/*.png
@include all-icon-sprites

.fb 
	@extend .icon-facebook
	width: image-width('icon/facebook.png')
	height: image-height("icon/facebook.png")
```



### other 
```
--------------------------
gulp
webpack
ejs 樣板語言(node.js)
npm install bootstrap
BME css 命名
主題化 bootstrap
codepen --> search steps
```





