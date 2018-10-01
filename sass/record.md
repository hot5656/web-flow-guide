# jQuery record

*   [Root](../README.md)
*   [1. variable](#a1)
*   [2. install compile](#a2)
*   [3. config.rb modify](#a3)
*   [4. import other scss file](#a4)
*   [5. mixin - 幫助記住css技巧](#a5)
*   [6. mixin - RWD](#a6)


<h2 id="a1">1. variable</h2>

```
// varibale start from $
$font-stack:    Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}
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

```

<h2 id="a5">5. mixin - 幫助記住css技巧</h2>

```
	@mixin hide-text {
		text-indent:110%
		white-space: nowarp;
		overflow: hidden;
  }
  .header h1 {
    	@include hide-text
  }
```

*   [6. mixin - RWD](#a6)
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