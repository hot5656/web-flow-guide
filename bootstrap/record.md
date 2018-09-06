# Bootstrap record

*   [Root](../README.md)
*   [1. Viewport](#a1)
*	[2. Basic](#a2)
*	[3. Class](#a3)
*	[4. Space](#a4)
*	[5. Size](#a5)
*	[6. Color](#a6)
*	[7. Border](#a7)
*	[8. Grid](#a8)

<h2 id="a1">1. Viewport</h2>

```
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
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
w-105 Width 100%

h-25 Height  25%
h-50 Height  55%
h-75 Height  75%
h-105 Height  100%

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