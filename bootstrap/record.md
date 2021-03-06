# Bootstrap record

* [Root](../README.md)
* [1. Viewport](#a1)
*	[2. Basic](#a2)
*	[3. Class](#a3)
*	[4. Space](#a4)
*	[5. Size](#a5)
*	[6. Color](#a6)
*	[7. Border](#a7)
*	[8. Grid](#a8)
* [9. Overwrite bootstrap(customize)](#a9)
* [10. Basic Body](#a10)
* [11. nav/navbar](#a11)
* [12. RWD simple](#a12)
* [13. flex](#a13)
* [14. 元件](#a14)
* [15. list](#a15)
* [16. tool plug](#a16)

<h2 id="a1">1. Viewport</h2>

```
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
Gecko 引擎的 Firefox mobile 上，確會讓使用者看到桌面版的網頁 : set shrink-to-fit=no"
```


<h2 id="a2">2. Basic</h2>

```
<!-- local Bootstrap CSS -->
<link rel="stylesheet" href="stylesheets/bootsrap/4.1.3/bootstrap-custom.css">
    
<!-- jQuery , Popper.js then Bootstrap JS -->
<script src="https://code.jquery.com/jquery-3.3.1.min.js" integrity="sha256-FgpCb/KJQlLNfOu91ta32o/NMZxltwRo8QtmkMRdAu8=" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js" integrity="sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js" integrity="sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy" crossorigin="anonymous"></script>
```

<h2 id="a3">3. Class</h2>

```
container/container-fluid : container width
form-inline : for linline
bg-transparent
form-control : input
navbar-expand : nav 往左靠
```


<h2 id="a4">4. Space</h2>
### 屬性 設定
```
m - 這個 class 會設定 margin
p - 這個 class 會設定 padding
```

### 邊緣 設定
```
t - 這個 class 會設定 margin-top 或 padding-top
b - 這個 class 會設定 margin-bottom 或 padding-bottom
l - 這個 class 會設定 margin-left 或 padding-left
r - 這個 class 會設定 margin-right 或 padding-right
x - 這個 class 會設定 *-left 和 *-right
y - 這個 class 會設定 *-top 和 *-bottom
空白 - 如果邊緣 class 未加入則會設定 margin 或 padding 在元素的四個邊緣
```

### 尺寸 設定
```
0 - 這個 class 會設定 margin 或 padding 的樣式值為 0
1 - (預設時) 這個 class 會設定 margin 或 padding 於 $spacer * .25
2 - (預設時) 這個 class 會設定 margin 或 padding 於 $spacer * .5
3 - (預設時) 這個 class 會設定 margin 或 padding 於 $spacer
4 - (預設時) 這個 class 會設定 margin 或 padding 於 $spacer * 1.5
5 - (預設時) 這個 class 會設定 margin 或 padding 於 $spacer * 3
auto - 這個 class 會設定 margin 為 auto

你也可以對 $spacers Sass map 調整變數
```

### Example
```
.mt-0 {
  margin-top: 0 !important;
}

.ml-1 {
  margin-left: ($spacer * .25) !important;
}

.px-2 {
  padding-left: ($spacer * .5) !important;
  padding-right: ($spacer * .5) !important;
}

.p-3 {
  padding: $spacer !important;
}
```

### 水平置中
```
.mx-auto 用於固定寬度盒模型的水平置中，是具有 display: block 和 width 集合的內容，並將水平 margin 設置為auto。
```


<h2 id="a5">5. Size</h2>

```
w-25 Width 25%
w-50 Width 55%
w-75 Width 75%
w-100 Width 100%

h-25 Height  25%
h-50 Height  55%
h-75 Height  75%
h-100 Height  100%

mw-100 max-width
mh-100 max-height
```

<h2 id="a6">6. Color</h2>

```
.text-primary
.text-secondary
.text-success
.text-danger
.text-warning
.text-info
.text-light
.text-dark
.text-muted
.text-white
情境色彩也提供 hover 和 focus狀態，對於連結類型也同時能順利運行。注意，.text-white、.text-muted 沒有連結樣式。

.bg-primary
.bg-secondary
.bg-success
.bg-danger
.bg-warning
.bg-info
.bg-light
.bg-dark
.bg-white

背景漸層
當 $enable-gradients 設置為true時，您將可以使用 .bg-gradient- 的通用類別。 預設情況下，$enable-gradients 是停用的，
```

<h2 id="a7">7. Border</h2>

```
border
border-top
border-right
border-bottom
border-left

border-0
border-top-0
border-right-0
border-bottom-0
border-left-0

border border-primary
border border-secondand
border border-success
border border-danger
border border-warning
border border-info
border border-light
border border-dark
border border-white

rounded
rounded-top
rounded-right
rounded-bottom
rounded-left
rounded-circle
rounded-0
```

<h2 id="a8">8. Grid</h2>


xx    	|Extra small|Small |Medium|Large |Extra large
--------|-----------|------|------|------|-----------
  		|<576px		|≥576px|≥768px|≥992px|≥1200px
Max container width|None (auto)|540px|	720px|960px|1140px
Class prefix|.col-|.col-sm-|.col-md-|.col-lg-|.col-xl-

Gutter width : 30px (15px on each side of a column)


<h2 id="a9">9. Overwrite bootstrap(customize)</h2>

### using by node.js 
```css
// install bootstrap css
npm install bootstrap --save-dev

// sass process
gulp.task('sass', () => {
  // PostCSS AutoPrefixer
  const processors = [
    autoprefixer({
      browsers: ['last 5 version'],
    }),
  ];

  return gulp
    .src(['./source/sass/**/*.sass', './source/sass/**/*.scss'])
    .pipe($.wait(200))
    .pipe($.plumber())
    .pipe($.sourcemaps.init())
    .pipe(
      $.sass({
        outputStyle: 'nested',
        includePaths: ['./node_modules/bootstrap/scss'],		// addition include sass
      }).on('error', $.sass.logError),
    )
    .pipe($.postcss(processors))
    .pipe($.if(options.env === 'production', $.cleanCss())) // 假設開發環境則壓縮 CSS
    .pipe($.sourcemaps.write('.'))
    .pipe(gulp.dest('./public/css'))
    .pipe(
      browserSync.reload({
        stream: true,
      }),
    );
});



// include bt
@import functions
@import bt_variables
@import bootstrap

// bareakpoint example for sass
// xl: 1200px
// lg: 992px
// md: 768px
// sm: 576px
// xs: 0
// +media-breakpoint-down(xl)
// +media-breakpoint-down(lg)
// +media-breakpoint-down(md)
// +media-breakpoint-down(sm)
// +media-breakpoint-down(xs)

$primary:       red; //$blue !default;
$secondary:     $gray-600 !default;
$success:       $green !default;
$info:          $cyan !default;

// change color
$primary:       $c-primary;   // $blue !default;
$secondary:     $c-secondary; // $gray-600 !default;
$info:          $c-info;      // $cyan !default;
$warning:       $c-warning;   // $yellow !default;

// add space 
$spacers: map-merge(
  (
    n90: -90px, // add
    20: 20px,   // add
    30: 30px,   // add
    50: 50px,   // add
    80: 80px,   // add
    105: 105px, // add
    0: 0,
    1: ($spacer * .25),
    2: ($spacer * .5),
    3: $spacer,
    4: ($spacer * 1.5),
    5: ($spacer * 3)
  ),
  $spacers
);

// modify break point
$grid-breakpoints: (
  xs: 0,
  sm: 576px,
  md: 768px,
  lg: 992px,
  xl: 1200px
);

// modify container max width
$container-max-widths: (
  sm: 540px,
  md: 720px,
  lg: 970px, //960px,
  xl: 1140px
) !default;

// changr navbar color for light
$navbar-light-color:                rgba($primary, .5); // rgba($black, .5) !default;
$navbar-light-hover-color:          rgba($primary, .7); // rgba($black, .7) !default;
$navbar-light-active-color:         rgba($primary, .9); // rgba($black, .9) !default; 

// button example 
<button type="button" class="btn btn-primary">Primary</button>
<button type="button" class="btn btn-secondary">Secondary</button>
<button type="button" class="btn btn-success">Success</button>
<button type="button" class="btn btn-danger">Danger</button>
<button type="button" class="btn btn-warning">Warning</button>
<button type="button" class="btn btn-info">Info</button>
<button type="button" class="btn btn-light">Light</button>
<button type="button" class="btn btn-dark">Dark</button>
<button type="button" class="btn btn-link">Link</button>
```

```css
// install bootstrap js
npm install gulp-concat --save-dev
npm install gulp-sequence --save-dev
npm install jquery --save-dev

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>甜點電商 - <%- title %></title>
</head>
<body>
  ................

  <!-- js -->
  <script src="js/vendor.js"></script>
</body>
</html>

const gulpSequence = require('gulp-sequence').use(gulp);
gulp.task('vendorJs', () => {
  return gulp
    .src([
      './node_modules/jquery/dist/jquery.slim.min.js',
      './node_modules/bootstrap/dist/js/bootstrap.bundle.min.js',
    ])
    .pipe($.concat('vendor.js'))
    .pipe(gulp.dest('./public/js'));
});
gulp.task('build', gulpSequence('clean', 'copy', 'sass', 'vendorJs', 'layout', 'sass'));
gulp.task('default', ['copy', 'sass', 'vendorJs', 'layout', 'browserSync', 'watch']);
```

<h2 id="a10">10. Basic Body</h2>

```html
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
<body>
  <div class="wrap container">
    <header>
    </header>
    <div class="content container">
    </div>
    <footer class="bg-gray1 pb-1 pt-3">
    </footer>
  </div>
</body>   
```

<h2 id="a11">11. nav bar</h2>

### nav
```html
<nav class="nav nav-pills nav-fill">
  <a class="nav-item nav-link" href="#">Active</a>
  <a class="nav-item nav-link active" href="#">Longer nav link</a>
  <a class="nav-item nav-link" href="#">Link</a>
  <a class="nav-item nav-link disabled" href="#">Disabled</a>
</nav
justify-content-center : 置中
justify-content-end : 靠右對齊
flex-column/flex-sm-column : 垂直
nav-tabs : 分頁標籤
nav-pills : 填滿背景 (add nav-justified also same)
nav-fill : 照比例分配空間

// support flex class

// 帶下拉選單的分頁標籤
ul class="nav nav-tabs">
  <li class="nav-item">
    <a class="nav-link active" href="#">Active</a>
  </li>
  <li class="nav-item dropdown">
    <a class="nav-link dropdown-toggle" data-toggle="dropdown" href="#" role="button" aria-haspopup="true" aria-expanded="false">Dropdown</a>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Action</a>
      <a class="dropdown-item" href="#">Another action</a>
      <a class="dropdown-item" href="#">Something else here</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Separated link</a>
    </div>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" href="#">Disabled</a>
  </li>
</ul>

//動態頁籤介面
// data-toggle="tab"
// data-toggle="pill" 
<nav>
  <div class="nav nav-tabs" id="nav-tab" role="tablist">
    <a class="nav-item nav-link active" id="nav-home-tab" data-toggle="tab" href="#nav-home" role="tab" aria-controls="nav-home" aria-selected="true">Home</a>
    <a class="nav-item nav-link" id="nav-profile-tab" data-toggle="tab" href="#nav-profile" role="tab" aria-controls="nav-profile" aria-selected="false">Profile</a>
    <a class="nav-item nav-link" id="nav-contact-tab" data-toggle="tab" href="#nav-contact" role="tab" aria-controls="nav-contact" aria-selected="false">Contact</a>
  </div>
</nav>
<div class="tab-content" id="nav-tabContent">
  <div class="tab-pane fade show active" id="nav-home" role="tabpanel" aria-labelledby="nav-home-tab">...</div>
  <div class="tab-pane fade" id="nav-profile" role="tabpanel" aria-labelledby="nav-profile-tab">...</div>
  <div class="tab-pane fade" id="nav-contact" role="tabpanel" aria-labelledby="nav-contact-tab">...</div>
</div>
```

### navbar
```html
.navbar + .navbar-light : 設定 navbar 顏色
navbar-expand-md : 設定 navbar 導覽列折疊點
.collapse.navbar-collapse : navbar 外層中斷點群組和隱藏導覽列內容
navbar-brand: navbar brand

// basic
使用 navbar
navbar-expand{-sm|-md|-lg|-xl} navbar 展開
navbar-light 
bg-light
// other 
navbar-brand 為您的公司，產品或專案名稱。
navbar-nav : nav item block
navbar-toggler 用於我們的折疊插件和其他 navigation toggling 行為。
form-inline : set form inline-block。
navbar-text : navbar 顯示文字
navbar-toggler-icon : 漢堡 icon
collapse : 摺疊
navbar-collapse : navbar 摺疊
// aria 旋律,盲人使用資料
aria-controls="navbarSupportedContent" : control map id
aria-expanded="false" : 未展開
aria-label="Toggle navigation"> : 說明
<span class="sr-only">(current)</span> : bootstrap for 螢幕閱讀器(隱藏)
flex-grow-0 : set flex-group 0

// navbar-brand
<!-- As a link -->
<nav class="navbar navbar-light bg-light">
  <a class="navbar-brand" href="#">Navbar</a>
</nav>

<!-- As a heading -->
<nav class="navbar navbar-light bg-light">
  <span class="navbar-brand mb-0 h1">Navbar</span>
</nav>


<!-- navbar 垂直 -->
<nav class="navbar">
  <ul class="navbar-nav">
    <li class="nav-item">
      <a class="nav-link" href="">首頁</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" href="">甜點</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" href="">登入</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" href="">Buy</a>
    </li>
  </ul>
</nav>

<!-- navbar 水平(navbar-expand) -->
<nav class="navbar navbar-expand">
  <ul class="navbar-nav">
    <li class="nav-item">
      <a class="nav-link" href="">首頁</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" href="">甜點</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" href="">登入</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" href="">Buy</a>
    </li>
  </ul>
</nav>

<!-- navbar add brand(navbar-brand) + 中間空白(justify-content-between)-->
<nav class="navbar navbar-expand justify-content-between">
  <a href="#" class="navbar-brand">
    <img src="img/logo.svg" alt="" style="height:40px">
    <img src="img/logotype-sm-dark.svg" alt="" style="height:30px">
  </a>
  <ul class="navbar-nav">
    <li class="nav-item">
      <a class="nav-link" href="">首頁</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" href="">甜點</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" href="">登入</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" href="">Buy</a>
    </li>
  </ul>
</nav>
```

```html
// sample
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Navbar</a>
  <!-- 漢堡式選單按鈕,摺疊時顯示 -->
  <!-- 擺於右邊,若要擺在左邊移植navbar-brand之前 -->
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <div class="navbar-nav mr-auto"">
      <a class="nav-item nav-link active" href="#">Home</a>
      <a class="nav-item nav-link" href="#">Features</a>
      <a class="nav-item nav-link" href="#">Pricing</a>
      <a class="nav-item nav-link disabled" href="#">Disabled</a>
    </div>
    <form class="form-inline my-2 my-lg-0">
      <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
      <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
    </form>
  </div>
</nav>
```



<h2 id="a12">12. RWD simple</h2>

```html
// col-sm-x 分一階 >=576
// col-sm-x col-md-x 分二階 >=576 >=768



```


<h2 id="a13">13. flex</h2>

### also support RWD
```
d-flex
d-inline-flex

flex-row : 設定水平的方向(default)
flex-row-reverse : 水平方向的反轉
flex-column : 設置垂直方向
flex-column-reverse : 垂直方向的反轉

// justify-content 通用類別改變 flex 物件在主軸上的對齊（x軸開始，如果 flex-direction: column，則為 y 軸）
justify-content-start
justify-content-end
justify-content-center
justify-content-between
justify-content-around

// align-items 工具改變橫軸上 flex 物件的對齊（y 軸開始，如果 flex-direction: column，則為 x 軸）
align-items-start
align-items-end
align-items-center
align-items-baseline
align-items-stretch : 瀏覽器預設

// align-self 通用類別單獨改變在橫軸上的對齊（y 軸開始，如果 flex-direction: column，則為 x 軸）。與 align-items 相同的選項
align-self-start
align-self-end
align-self-center
align-self-baseline
align-self-stretch : 瀏覽器預設

//強制它們在相同的寬度上分配所有可用的水平空間
flex-fill

// 索取剩餘空間比例 default = 0
flex-grow-*
flex-grow-1 : 佔一份

// 縮小比例 default = 0
flex-shrink-*
flex-shrink-1 : 縮小比例 1
flex-shrink-2 : 縮小比例 2
flex-shrink-3 : 縮小比例 3

// 容器超過處理
flex-nowrap : 不顯示往下
flex-wrap : 顯示往下
flex-wrap-reverse : 反轉顯示

// 順序調整
order-0~12

// 多行控制 align-content(when flex-wrap)
align-content-start
align-content-end
align-content-center
align-content-between
align-content-around
align-content-stretch : 預設值，內容元素全部撐開

```

### margin support
```
<div class="d-flex bd-highlight mb-3">
  <div class="mr-auto p-2 bd-highlight">Flex item</div>
  <div class="p-2 bd-highlight">Flex item</div>
  <div class="p-2 bd-highlight">Flex item</div>
</div>

<div class="d-flex align-items-start flex-column bd-highlight mb-3" style="height: 200px;">
  <div class="mb-auto p-2 bd-highlight">Flex item</div>
  <div class="p-2 bd-highlight">Flex item</div>
  <div class="p-2 bd-highlight">Flex item</div>
</div>
```

<h2 id="a14">14. 元件</h2>

### 警報 (Alerts)

```css

```

### 分頁 (Pagination)

```
ul(pagination) > li(page-item+active/disable) > a(page-link)

<ul class="pagination justify-content-center pagination-lg">
	<li class="page-item disabled"><a href="#" class="page-link"><</a></li>
	<li class="page-item active"><a href="#" class="page-link">1</a></li>
	<li class="page-item"><a href="#" class="page-link">2</a></li>
	<li class="page-item"><a href="#" class="page-link">3</a></li>
	<li class="page-item"><a href="#" class="page-link">4</a></li>
	<li class="page-item"><a href="#" class="page-link">></a></li>
</ul>
```

### btn
```
btn-lg/btn-sm : 較大或較小的按鈕
btn-block : 等同於外元素的寬 
active : 套用相同的啟用外觀
-- 透過將 disabled 布林屬性添加到任何 <button> 元素，使按鈕看起來處於停用狀態
<button type="button" class="btn btn-lg btn-primary" disabled>Primary button</button>
-- 增加 data-toggle="button" 來切換按鈕 active 狀態。 如果您預先需要切換按鈕，則必須手動將 .active class 和 aria-pressed="true" 添加到 <button> 中
<button type="button" class="btn btn-primary" data-toggle="button" aria-pressed="false" autocomplete="off">
  Single toggle
</button>
```

### a
```
---不支援 disabled 屬性，所以你必須添加 .disabled 使它在視覺上看起來被禁用
<a href="#" class="btn btn-primary btn-lg disabled" role="button" aria-disabled="true">Primary link</a>
```

<h2 id="a15">15. list</h2>

```css
// container : container > row(no-gutters) > col-x : grid  
container/container-fluid : 固定寬度/滿版寬度
	// row
	container 左右各有 15px padding, default row 會設定 margin -15px 補置對齊 container 
	no-gutters : 從行中移除邊緣 margin(row-container間會有間隔),從欄中移除填充 padding(col data 間無間隔)
	// col
	col-12.col-md-4 : set col #
	col-sm*4 : 均分為4等份
	col-auto : 依內容物調整 
	// row + 對齊水平和垂直 (also d-flex using)
	x 對齊
		.justify-content-sm-start
		.justify-content-sm-end
		.justify-content-sm-center
		.justify-content-sm-between
		.justify-content-sm-around
	y 對齊
		.align-items-sm-start
		.align-items-sm-end
		.align-items-sm-center
		.align-items-sm-baseline
		.align-items-sm-stretch
	// col + 對齊垂直 (also d-flex using)
	y 對齊 align-self-start
		.align-self-sm-start
		.align-self-sm-end
		.align-self-sm-center
		.align-self-sm-baseline
		.align-self-sm-stretch (全高度)
	// w-100 
	可換行
	<!-- Force next columns to break to new line at md breakpoint and up -->
  <div class="w-100 d-none d-md-block"></div>
	// order 1~12 order-first, order-last
	<div class="col order-first">xx</div>
	// offset
	<div class="col-md-4 offset-md-4">.col-md-4 .offset-md-4</div>
	// margin - .mr-auto/.ml-auto 將相鄰的欄位分離到另一邊
	<div class="row">
	  <div class="col-md-4">.col-md-4</div>
	  <div class="col-md-4 ml-auto">.col-md-4 .ml-auto</div>
	</div>
	// 巢狀
	<div class="row">
	  <div class="col-sm-9">
	    Level 1: .col-sm-9
	    <div class="row">
	      <div class="col-8 col-sm-6">
	        Level 2: .col-8 .col-sm-6
	      </div>
	      <div class="col-4 col-sm-6">
	        Level 2: .col-4 .col-sm-6
	      </div>
	    </div>
	  </div>
	</div>
// conatiner - use mixin
	-----> mixin
	// Creates a wrapper for a series of columns
	@include make-row();
	// Make the element grid-ready (applying everything but the width)
	@include make-col-ready();
	@include make-col($size, $columns: $grid-columns);
	// Get fancy by offsetting, or changing the sort order
	@include make-col-offset($size, $columns: $grid-columns);
	-----> custmize example
	...wait
// set mode
	d-xx-inline-block/d-xx-none/d-xx-block/d-xx-flex : 設定為 inline-block/no show/block/flex
// d-flex
	align-items-center/justify-content-center/justify-content-md-end : flax position
	.flex-xx-row(default)/.flex-xx-row-reverse(set reverse)
	.flex-xx-column(set column)/.flex-xx-column-reverse(set column reverse)
 	.flex-xx-nowrap(default)/.flex-xx-wrap/.flex-xx-wrap-reverse
	.order-xl-1 ~ .order-xl-12 
// 分左右(可巢狀) .media and .media-body
	--> example 
	<div class="media">
	  <img class="mr-3" src=".../64x64" alt="Generic placeholder image">
	  <div class="media-body">
	    <h5 class="mt-0">Media heading</h5>
	    Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
	  </div>
	</div>
	--> 調整前段位置(上/中/下) - align-self-center
	<div class="media">
	  <img class="align-self-center mr-3" src=".../64x64" alt="Generic placeholder image">
	  <div class="media-body">
	    <h5 class="mt-0">Center-aligned media</h5>
	    <p>Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.</p>
	    <p class="mb-0">Donec sed odio dui. Nullam quis risus eget urna mollis ornare vel eu leo. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.</p>
	  </div>
	</div>
// 可見,不可見(但影響布局)
	<div class="visible">...</div>
	<div class="invisible">...</div>
// 字體 - 不同系統使用不同字體
	$font-family-sans-serif:
	  // Safari for OS X and iOS (San Francisco)
	  -apple-system,
	  // Chrome < 56 for OS X (San Francisco)
	  BlinkMacSystemFont,
	  // Windows
	  "Segoe UI",
	  // Android
	  "Roboto",
	  // Basic web fallback
	  "Helvetica Neue", Arial, sans-serif,
	  // Emoji fonts
	  "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol" !default;
// set 字型大小 class
	.h1 ~ .h6
	.display-1 ~ display-4
// 段落突出
	.lead
// 行內文本元素(使用行內 HTML5 元素的格式)
	<p>You can use the mark tag to <mark>highlight</mark> text.</p>
	del : <p><del>This line of text is meant to be treated as deleted text.</del></p>
	<p><s>This line of text is meant to be treated as no longer accurate.</s></p>
	<p><ins>This line of text is meant to be treated as an addition to the document.</ins></p>
	under line : <p><u>This line of text will render as underlined</u></p>
	small : <p><small>This line of text is meant to be treated as fine print.</small></p>
	strong : <p><strong>This line rendered as bold text.</strong></p>
	斜體 : <p><em>This line rendered as italicized text.</em></p>
// 縮寫
	用 HTML <abbr> 元素以 Hover 方式顯示縮寫的擴增內容
	向一個縮寫中加入 .initialism 可將字體略為縮小
	<p><abbr title="attribute">attr</abbr></p>
	<p><abbr title="HyperText Markup Language" class="initialism">HTML</abbr></p>
// 引用
	使用 <blockquote class="blockquote"> 包括在 HTML 周圍。
	<blockquote class="blockquote">
		<p class="mb-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
	</blockquote>
// 引用來源
	添加一個 <footer class="blockquote-footer"> 以便識別來源。將來源的名稱包在 <cite> 中。
	<blockquote class="blockquote">
		<p class="mb-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
		<footer class="blockquote-footer">Someone famous in <cite title="Source Title">Source Title</cite></footer>
	</blockquote>
// 文字 (Text)
	.text-justify : 文件與元件對齊 ??
	.text-xx-left
	.text-xx-cente
	.text-xx-right
	.text-nowrap : 防止換行
	.text-lowercase
	.text-uppercase
	.text-capitalize : 第一個字大寫
	.font-weight-bold
	.font-weight-normal
	.font-weight-light
	.font-italic
	.text-monospace : 將選擇區域改為等寬字體
		<p class="text-monospace">This is in monospace</p>
// img
	.img-fluid : 讓圖片可依父元素屬性進行縮放(set max-width)
	.img-thumbnail : 讓圖片有1px邊框的顯示 and 4px padding
	.rounded : 圓角
	.float-left : 靠左
	.float-right : 靠右
// table
	.table : 基本樣式
	.table-dark : 設定為深色表格
	.thead-light/.thead-dark : <thead> head background color
  .table-striped(<table>) : 加入斑馬紋
	.table-bordered(<table>) : 加入外框
 	.table-borderless(<table>) : 無分隔線
 	.table-hover(<table>) : hover 列,會更改被景色
	.table-sm(<table>) : 縮小table之padding(table 高度會較小)
	--> table color (table-dark not support, you can use bg-primary ....)
		table-active,table-dark,table-light,table-primary ... 
	.table-responsive-sm : table 在 sm 且過長時,會有水平滾動條
		<div class="table-responsive-sm">
		  <table class="table">
		    ...
		  </table>
		</div>
	<caption> : 表格標題(可以協助螢幕閱讀器的用戶找到表格，並了解它的內容，且決定是否要閱讀它)
		<table class="table">
		  <caption>List of users</caption>
		  <thead>
		    <tr>
		      <th scope="col">#</th>
		      <th scope="col">First</th>
		      <th scope="col">Last</th>
		      <th scope="col">Handle</th>
		    </tr>
		  </thead>
		  <tbody>
		    <tr>
		      <th scope="row">1</th>
		      <td>Mark</td>
		      <td>Otto</td>
		      <td>@mdo</td>
		    </tr>
		  </tbody>
		</table>
// set background 
	bg-primary,bg-succes, ....
// aligment
	mx-5 : set x side margin
	px-5 : set y padding
	mx-auto : 置中
```

### mixin

```
// 由小而大
+media-breakpoint-up(md)
// 由大而小
+media-breakpoint-down(sm)
// 某些範圍
+media-breakpoint-only(xs)
// 可見,不可見(但影響布局)
+invisible(visible)
+invisible(hidden)
```


<h2 id="a6">16. tool plug</h2>

```
sublime : Bootstrap 4 Snippets
```

```