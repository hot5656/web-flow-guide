# sass record

*   [Root](../README.md)
*   [1. variable](#a1)
*   [2. install compile](#a2)
*   [3. config.rb modify](#a3)
*   [4. import other scss file](#a4)
*   [5. mixin - 幫助記住css技巧](#a5)
*   [6. mixin - RWD](#a6)
*   [7. 加減乘除](#a7)
*   [8. sector標誌](#a8)
*   [9. @extend合併css](#a9)
*   [10. compass](#a10)
*   [11. mixin example](#a11)
*   [12. sass init example](#a12)


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
```

<h2 id="a4">4. import other scss file</h2>

```
// prepare for import scss(_ start)
		@import 'mixin'
		@import 'reset'
		@import 'layout'
		@import 'module'	//btuuon,form,gtable	

// sass
	@import reset
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


<h2 id="a6">6. mixin - RWD</h2>

```
// screen
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


// sass function - runy support but vscode not support   
width: image-width("../img/#{$name}.#{$sub}")
height: image-height("../img/#{$name}.#{$sub}")
```

<h2 id="a11">11. mixin example</h2>

```
// background image
@mixin bg($name,$sub)
  background-image: url("../img/#{$name}.#{$sub}")
  width: image-width("../img/#{$name}.#{$sub}")
  height: image-height("../img/#{$name}.#{$sub}")
// hide text
@mixin hide-text
  white-space: nowrap	// 空白的處理方法 連續的空白字會縮減為一個空白，不跳行
  text-indent: 100%		// 讓首行縮排 100%
  overflow: hidden
```

<h2 id="a12">12. sass init example</h2>

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

--------------------------
gulp
webpack
ejs 樣板語言(node.js)
npm install bootstrap
BME css 命名
主題化 bootstrap
codepen --> search steps






