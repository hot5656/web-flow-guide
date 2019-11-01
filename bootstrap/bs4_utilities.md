## [Bootstrap 4 Guide](./bootstrap4_guide.md)
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<meta http-equiv="X-UA-Compatible" content="ie=edge">
	<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
	<title>BS4 utilities</title>
</head>
<body>

<!-- Optional JavaScript -->
<!-- jQuery first, then Popper.js, then Bootstrap JS -->
<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
</body>
</html>

<link rel="stylesheet" href="bootstrap4_exaample.css">

## BS4 utilities
* [Spacing-間隔](#Spacing)
* [Color](#Color)
* [Boards](#Boards)
* [Clearfix](#Clearfix)
* [CloseIcon](#CloseIcon)
* [Display](#Display)
* [Embeds-內嵌](#Embeds)
* [Flex](#Flex)
* [Float-浮動](#Float)
* [ImageReplacement-圖像替換](ImageReplacement)
* [Overflow](#Overflow)
* [Position](#Position)
* [Shadows](#Shadows)
* [Sizing](#Sizing)
* [Text-文字](#Text)
* [VerticalAlignment-垂直對齊](#VerticalAlignment)
* [Visibility-可見性](#Visibility)

<a id="Spacing"></a>
## Spacing [[Home]](#)  

* 屬性 設定:
```
m - 這個 class 會設定 margin
p - 這個 class 會設定 padding
```

* 邊緣 設定:
```
t - 這個 class 會設定 margin-top 或 padding-top
b - 這個 class 會設定 margin-bottom 或 padding-bottom
l - 這個 class 會設定 margin-left 或 padding-left
r - 這個 class 會設定 margin-right 或 padding-right
x - 這個 class 會設定 *-left 和 *-right
y - 這個 class 會設定 *-top 和 *-bottom
空白 - 如果邊緣 class 未加入則會設定 margin 或 padding 在元素的四個邊緣
```

* 尺寸 設定:
```
0 - 這個 class 會設定 margin 或 padding 的樣式值為 0
1 - (預設時) 這個 class 會設定 margin 或 padding 於 $spacer * .25
2 - (預設時) 這個 class 會設定 margin 或 padding 於 $spacer * .5
3 - (預設時) 這個 class 會設定 margin 或 padding 於 $spacer
4 - (預設時) 這個 class 會設定 margin 或 padding 於 $spacer * 1.5
5 - (預設時) 這個 class 會設定 margin 或 padding 於 $spacer * 3
auto - 這個 class 會設定 margin 為 auto
```

* 水平置中  
<div class="mx-auto bg-light" style="width: 200px;">
  Centered element
</div>

```html
<div class="mx-auto" style="width: 200px;">
  Centered element
</div>
```

* Negative margin  
margin 屬性可以使用負值（padding 不能） , n1~n5  
<div class="container py-2 border">
	<div class="row mx-n5 bg-light">
	  <div class="col border">Custom column padding</div>
	  <div class="col border">Custom column padding</div>
	</div>
</div>

```html
<div class="container">
	<div class="row mx-n5">
	  <div class="col">Custom column padding</div>
	  <div class="col">Custom column padding</div>
	</div>
</div>
```


<a id="Color"></a>
## Color [[Home]](#)  

* text  
<p class="text-primary">.text-primary</p>
<p class="text-secondary">.text-secondary</p>
<p class="text-success">.text-success</p>
<p class="text-danger">.text-danger</p>
<p class="text-warning">.text-warning</p>
<p class="text-info">.text-info</p>
<p class="text-light bg-dark">.text-light</p>
<p class="text-dark">.text-dark</p>
<p class="text-body">.text-body</p>
<p class="text-muted">.text-muted</p>
<p class="text-white bg-dark">.text-white</p>
<p class="text-black-50">.text-black-50</p>
<p class="text-white-50 bg-dark">.text-white-50</p>

```html
<p class="text-primary">.text-primary</p>
<p class="text-secondary">.text-secondary</p>
<p class="text-success">.text-success</p>
<p class="text-danger">.text-danger</p>
<p class="text-warning">.text-warning</p>
<p class="text-info">.text-info</p>
<p class="text-light bg-dark">.text-light</p>
<p class="text-dark">.text-dark</p>
<p class="text-body">.text-body</p>
<p class="text-muted">.text-muted</p>
<p class="text-white bg-dark">.text-white</p>
<p class="text-black-50">.text-black-50</p>
<p class="text-white-50 bg-dark">.text-white-50</p>
```

* Background  
<div class="p-3 mb-2 bg-primary text-white">.bg-primary</div>
<div class="p-3 mb-2 bg-secondary text-white">.bg-secondary</div>
<div class="p-3 mb-2 bg-success text-white">.bg-success</div>
<div class="p-3 mb-2 bg-danger text-white">.bg-danger</div>
<div class="p-3 mb-2 bg-warning text-dark">.bg-warning</div>
<div class="p-3 mb-2 bg-info text-white">.bg-info</div>
<div class="p-3 mb-2 bg-light text-dark">.bg-light</div>
<div class="p-3 mb-2 bg-dark text-white">.bg-dark</div>
<div class="p-3 mb-2 bg-white text-dark">.bg-white</div>
<div class="p-3 mb-2 bg-transparent text-dark">.bg-transparent</div>

```html
<div class="p-3 mb-2 bg-primary text-white">.bg-primary</div>
<div class="p-3 mb-2 bg-secondary text-white">.bg-secondary</div>
<div class="p-3 mb-2 bg-success text-white">.bg-success</div>
<div class="p-3 mb-2 bg-danger text-white">.bg-danger</div>
<div class="p-3 mb-2 bg-warning text-dark">.bg-warning</div>
<div class="p-3 mb-2 bg-info text-white">.bg-info</div>
<div class="p-3 mb-2 bg-light text-dark">.bg-light</div>
<div class="p-3 mb-2 bg-dark text-white">.bg-dark</div>
<div class="p-3 mb-2 bg-white text-dark">.bg-white</div>
<div class="p-3 mb-2 bg-transparent text-dark">.bg-transparent</div>
```

* Background gradient(背景漸層)  
當 $enable-gradients 設置為 true (預設是 false) 時，您將可以使用 .bg-gradient- 的通用類別。  
<div class="alert alert-info" role="alert">
	Don't check detail yet
</div>

```html
.bg-gradient-primary
.bg-gradient-secondary
.bg-gradient-success
.bg-gradient-danger
.bg-gradient-warning
.bg-gradient-info
.bg-gradient-light
.bg-gradient-dark
```


<a id="Boards"></a>
## Boards [[Home]](#)  

* Additive  
<span class="border board-block"></span>
<span class="border-top board-block"></span>
<span class="border-right board-block"></span>
<span class="border-bottom board-block"></span>
<span class="border-left board-block"></span>

```html
<span class="border"></span>
<span class="border-top"></span>
<span class="border-right"></span>
<span class="border-bottom"></span>
<span class="border-left"></span>
```

* Subtractive  
<span class="border-0 board-block"></span>
<span class="border-top-0 board-block"></span>
<span class="border-right-0 board-block"></span>
<span class="border-bottom-0 board-block"></span>
<span class="border-left-0 board-block"></span>

```html
<span class="border-0"></span>
<span class="border-top-0"></span>
<span class="border-right-0"></span>
<span class="border-bottom-0"></span>
<span class="border-left-0"></span>
```

* Border color
<div></div>
<span class="border-primary board-block"></span>
<span class="border-secondary board-block"></span>
<span class="border-success board-block"></span>
<span class="border-danger board-block"></span>
<span class="border-warning board-block"></span>
<span class="border-info board-block"></span>
<span class="border-light board-block"></span>
<span class="border-dark board-block"></span>
<span class="border-white board-block"></span>

```html
<span class="border border-primary"></span>
<span class="border border-secondary"></span>
<span class="border border-success"></span>
<span class="border border-danger"></span>
<span class="border border-warning"></span>
<span class="border border-info"></span>
<span class="border border-light"></span>
<span class="border border-dark"></span>
<span class="border border-white"></span>
```

* Border-radius
<div></div>
<img src="https://fakeimg.pl/75x75/" alt="..." class="rounded">
<img src="https://fakeimg.pl/75x75/" alt="..." class="rounded-top">
<img src="https://fakeimg.pl/75x75/" alt="..." class="rounded-right">
<img src="https://fakeimg.pl/75x75/" alt="..." class="rounded-bottom">
<img src="https://fakeimg.pl/75x75/" alt="..." class="rounded-left">
<img src="https://fakeimg.pl/75x75/" alt="..." class="rounded-circle">
<img src="https://fakeimg.pl/150x75/" alt="..." class="rounded-pill">
<img src="https://fakeimg.pl/75x75/" alt="..." class="rounded-0">

```html
<img src="..." alt="..." class="rounded">
<img src="..." alt="..." class="rounded-top">
<img src="..." alt="..." class="rounded-right">
<img src="..." alt="..." class="rounded-bottom">
<img src="..." alt="..." class="rounded-left">
<img src="..." alt="..." class="rounded-circle">
<img src="..." alt="..." class="rounded-pill">
<img src="..." alt="..." class="rounded-0">
```

* Sizes  
Use .rounded-lg or .rounded-sm for larger or smaller border-radius.

```html
<img src="..." alt="..." class="rounded-sm">
<img src="..." alt="..." class="rounded-lg">
```

<a id="Clearfix"></a>
## Clearfix [[Home]](#)  
Quickly and easily clear floated content within a container by adding a clearfix utility.  

```
<div class="bg-info clearfix">
  <button type="button" class="btn btn-secondary float-left">Example Button floated left</button>
  <button type="button" class="btn btn-secondary float-right">Example Button floated right</button>
</div>
```

<a id="CloseIcon"></a>
## CloseIcon [[Home]](#)  
aria-label="Close, aria-hidden="true" 是給螢幕閱讀器使用  
\&times; : Entity name for close symble  
default put to right  

<div class="clearfix">
	<button type="button" class="close" aria-label="Close">
	  <span aria-hidden="true">&times;</span>
	</button>
</div>

```html
<button type="button" class="close" aria-label="Close">
  <span aria-hidden="true">&times;</span>
</button>
```

<a id="Display"></a>
## Display [[Home]](#)  
.d-{value} for xs  
.d-{breakpoint}-{value} for sm, md, lg, and xl.  
> value support as below :  
	none  
	inline  
	inline-block  
	block  
	table  
	table-cell  
	table-row  
	flex  
	inline-flex  

```html
<span class="d-block p-2 bg-primary text-white">d-block</span>
<span class="d-block p-2 bg-dark text-white">d-block</span>
```

<a id="Embeds"></a>
## Embeds-內嵌 [[Home]](#)  
embed-responsive-21by9 : 長寬比 21:9  
embed-responsive-16by9 : 長寬比 16:9  
embed-responsive-4by3 : 長寬比 4:3  
embed-responsive-1by1 : 長寬比 1:1  

<div class="embed-responsive embed-responsive-16by9">
  <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/zpOULjyy-n8?rel=0" allowfullscreen></iframe>
</div>

```html
<!-- 21:9 aspect ratio -->
<div class="embed-responsive embed-responsive-21by9">
  <iframe class="embed-responsive-item" src="..."></iframe>
</div>

<!-- 16:9 aspect ratio -->
<div class="embed-responsive embed-responsive-16by9">
  <iframe class="embed-responsive-item" src="..."></iframe>
</div>

<!-- 4:3 aspect ratio -->
<div class="embed-responsive embed-responsive-4by3">
  <iframe class="embed-responsive-item" src="..."></iframe>
</div>

<!-- 1:1 aspect ratio -->
<div class="embed-responsive embed-responsive-1by1">
  <iframe class="embed-responsive-item" src="..."></iframe>
</div>
```

在_variables.scss 中，您可以更改要使用的寬高比  
```html
$embed-responsive-aspect-ratios: (
  (21 9),
  (16 9),
  (3 4),
  (1 1)
) !default;
```

<a id="Flex"></a>
## Flex [[Home]](#)  

* d-flex / d-inline-flex
<div class="d-flex p-2 bg-light m-2">I'm a flexbox container!</div>
<div class="d-inline-flex p-2 bg-light m-2">I'm an inline flexbox container!</div>

```html
<div class="d-flex p-2 bg-light">I'm a flexbox container!</div>
<div class="d-inline-flex p-2 bg-light">I'm an inline flexbox container!</div>
```

* 方向性  
.flex-row 來設定水平的方向  
.flex-row-reverse來作水平方向的反轉  
.flex-column 設置垂直方向  
.flex-column-reverse 作垂直方向的反轉  

<div class="d-flex flex-row text-white bg-light mb-3">
	<div class="p-2 bg-secondary border">Flex item 1</div>
	<div class="p-2 bg-secondary border">Flex item 2</div>
	<div class="p-2 bg-secondary border">Flex item 3</div>
</div>
<div class="d-flex flex-row-reverse text-white bg-light mb-3">
	<div class="p-2 bg-secondary border">Flex item 1</div>
	<div class="p-2 bg-secondary border">Flex item 2</div>
	<div class="p-2 bg-secondary border">Flex item 3</div>
</div>
<div class="d-flex flex-column text-white bg-light mb-3">
	<div class="p-2 bg-secondary border">Flex item 1</div>
	<div class="p-2 bg-secondary border">Flex item 2</div>
	<div class="p-2 bg-secondary border">Flex item 3</div>
</div>
<div class="d-flex flex-column-reverse text-white bg-light mb-3">
	<div class="p-2 bg-secondary border">Flex item 1</div>
	<div class="p-2 bg-secondary border">Flex item 2</div>
	<div class="p-2 bg-secondary border">Flex item 3</div>
</div>

```html
<div class="d-flex flex-row text-white bg-light mb-3">
	<div class="p-2 bg-secondary">Flex item 1</div>
	<div class="p-2 bg-secondary">Flex item 2</div>
	<div class="p-2 bg-secondary">Flex item 3</div>
</div>
<div class="d-flex flex-row-reverse text-white bg-light mb-3">
	<div class="p-2 bg-secondary">Flex item 1</div>
	<div class="p-2 bg-secondary">Flex item 2</div>
	<div class="p-2 bg-secondary">Flex item 3</div>
</div>
<div class="d-flex flex-column text-white bg-light mb-3">
	<div class="p-2 bg-secondary border">Flex item 1</div>
	<div class="p-2 bg-secondary border">Flex item 2</div>
	<div class="p-2 bg-secondary border">Flex item 3</div>
</div>
<div class="d-flex flex-column-reverse text-white bg-light mb-3">
	<div class="p-2 bg-secondary border">Flex item 1</div>
	<div class="p-2 bg-secondary border">Flex item 2</div>
	<div class="p-2 bg-secondary border">Flex item 3</div>
</div>
```

* 調整內容  
使用 flexbox 容器上的 justify-content 通用類別改變 flex 物件在主軸上的對齊（x軸開始，如果 flex-direction: column，則為 y 軸）  

<div class="d-flex justify-content-start text-white bg-light mb-3">
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
</div>
<div class="d-flex justify-content-end text-white bg-light mb-3">
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
</div>
<div class="d-flex justify-content-center text-white bg-light mb-3">
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
</div>
<div class="d-flex justify-content-between text-white bg-light mb-3">
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
</div>
<div class="d-flex justify-content-around text-white bg-light mb-3">
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
</div>

```html
<div class="d-flex justify-content-start">...</div>
<div class="d-flex justify-content-end">...</div>
<div class="d-flex justify-content-center">...</div>
<div class="d-flex justify-content-between">...</div>
<div class="d-flex justify-content-around">...</div>
```

* 對齊物件  
在 flexbox 容器上使用 align-items 工具改變橫軸上 flex 物件的對齊（y 軸開始，如果 flex-direction: column，則為 x 軸）  
從start、 end、 center、 baseline、 或 stretch (瀏覽器預設) 中選擇  

<div class="d-flex align-items-start text-white bg-light mb-3" style="height: 100px;">
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
</div>
<div class="d-flex align-items-end text-white bg-light mb-3" style="height: 100px;">
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
</div>
<div class="d-flex align-items-center text-white bg-light mb-3" style="height: 100px;">
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
</div>
<div class="d-flex align-items-baseline text-white bg-light mb-3" style="height: 100px;">
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
</div>
<div class="d-flex align-items-stretch text-white bg-light mb-3" style="height: 100px;">
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
</div>

```html
<div class="d-flex align-items-start">...</div>
<div class="d-flex align-items-end">...</div>
<div class="d-flex align-items-center">...</div>
<div class="d-flex align-items-baseline">...</div>
<div class="d-flex align-items-stretch">...</div>
```

* 自身對齊  
使用 flexbox 物件上的 align-self 通用類別單獨改變在橫軸上的對齊（y 軸開始，如果 flex-direction: column，則為 x 軸）  

<div class="d-flex text-white bg-light mb-3" style="height: 100px;">
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary align-self-start border">Aligned flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
</div>
<div class="d-flex text-white bg-light mb-3" style="height: 100px;">
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary align-self-end border">Aligned flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
</div>
<div class="d-flex text-white bg-light mb-3" style="height: 100px;">
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary align-self-center border">Aligned flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
</div>
<div class="d-flex text-white bg-light mb-3" style="height: 100px;">
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary align-self-baseline border">Aligned flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
</div>
<div class="d-flex text-white bg-light mb-3 borde" style="height: 100px;">
	<div class="p-2 bg-secondary border">Flex item</div>
	<div class="p-2 bg-secondary align-self-stretch border">Aligned flex item</div>
	<div class="p-2 bg-secondary border">Flex item</div>
</div>

```html
<div class="align-self-start">Aligned flex item</div>
<div class="align-self-end">Aligned flex item</div>
<div class="align-self-center">Aligned flex item</div>
<div class="align-self-baseline">Aligned flex item</div>
<div class="align-self-stretch">Aligned flex item</div>
```

* 填滿  
.flex-fill 填滿空間  

<div class="d-flex text-white bg-light mb-3">
	<div class="p-2 bg-secondary flex-fill border">Flex item with a lot of content</div>
	<div class="p-2 bg-secondary flex-fill border">Flex item</div>
	<div class="p-2 bg-secondary flex-fill border">Flex item</div>
</div>

```html
<div class="d-flex text-white bg-light">
	<div class="p-2 bg-secondary flex-fill">Flex item with a lot of content</div>
	<div class="p-2 bg-secondary flex-fill">Flex item</div>
	<div class="p-2 bg-secondary flex-fill">Flex item</div>
</div>
```

* 伸縮值  
.flex-grow-* 通用類別來切換項目彈性增長以填充可用空間  
.flex-grow-1 元素使用它可以使用的所有可用空間，同時允許剩餘的兩個 flex 物件保留必要的空間  
.flex-{grow|shrink}-0 / .flex-{grow|shrink}-1 

<div class="d-flex text-white bg-light mb-3">
  <div class="p-2 flex-grow-1 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Third flex item</div>
</div>

<div class="d-flex text-white bg-light mb-3">
  <div class="p-2 flex-grow-1 bg-secondary border">Flex item</div>
  <div class="p-2 flex-grow-1 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Third flex item</div>
</div>

```html
<div class="d-flex text-white bg-light mb-3">
  <div class="p-2 flex-grow-1 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Third flex item</div>
</div>

<div class="d-flex text-white bg-light mb-3">
  <div class="p-2 flex-grow-1 bg-secondary border">Flex item</div>
  <div class="p-2 flex-grow-1 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Third flex item</div>
</div>
```

.flex-shrink-* 通用類別來切換項目的縮小能力  
.flex-shrink-1 的第二個flex 項目的文字內容會被強制換行，”收縮” 以允許更多空間用於上一個帶有 .w-100 的 flex 物件  
<div class="d-flex text-white bg-light mb-3">
  <div class="p-2 w-100 bg-secondary border">Flex item</div>
  <div class="p-2 flex-shrink-1 bg-secondary border">Flex item</div>
</div>

```html
<div class="d-flex text-white bg-light mb-3">
  <div class="p-2 w-100 bg-secondary border">Flex item</div>
  <div class="p-2 flex-shrink-1 bg-secondary border">Flex item</div>
</div>
```

* 自動 margins  
IE10 和 IE11 在父層 justify-content 值並沒有正確的支援自動 margin 在 flex 元件上  
.mr-auto / .ml-auto  

<div class="d-flex text-white bg-light mb-3">
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
</div>

<div class="d-flex text-white bg-light mb-3">
  <div class="mr-auto p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
</div>

<div class="d-flex text-white bg-light mb-3">
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="ml-auto p-2 bg-secondary border">Flex item</div>
</div>

```html
<div class="d-flex text-white bg-light mb-3">
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
</div>

<div class="d-flex text-white bg-light mb-3">
  <div class="mr-auto p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
</div>

<div class="d-flex text-white bg-light mb-3">
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="ml-auto p-2 bg-secondary border">Flex item</div>
</div>
```

* 自動 margins 搭配 align-items  
.align-items-xx + flex-column 可使能安排於面  

<div class="d-flex align-items-start flex-column text-white bg-light mb-3" style="height: 200px;">
  <div class="mb-auto p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
</div>

<div class="d-flex align-items-end flex-column text-white bg-light mb-3" style="height: 200px;">
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="mt-auto p-2 bg-secondary border">Flex item</div>
</div>

```html
<div class="d-flex align-items-start flex-column text-white bg-light mb-3" style="height: 200px;">
  <div class="mb-auto p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
</div>

<div class="d-flex align-items-end flex-column text-white bg-light mb-3" style="height: 200px;">
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="mt-auto p-2 bg-secondary border">Flex item</div>
</div>
```

* Wrap
.flex-nowrap、.flex-wrap、.flex-wrap-reverse  
.flex-nowrap : 變形塞入(default)  
.flex-wrap /.flex-wrap-reverse : 不變形往下延伸  

<div class="d-flex text-white bg-light mb-3" style="width: 20rem;">
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
</div>

<div class="d-flex text-white bg-light mb-3 flex-nowrap" style="width: 20rem;">
  <div class="bg-secondary border">Flex item1</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
</div>

<div class="d-flex text-white bg-light mb-3 flex-wrap" style="width: 20rem;">
  <div class="bg-secondary border">Flex item1</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
</div>

<div class="d-flex text-white bg-light mb-3 flex-wrap-reverse" style="width: 20rem;">
  <div class="bg-secondary border">Flex item1</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
</div>

```html
<div class="d-flex text-white bg-light mb-3" style="width: 20rem;">
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
</div>

<div class="d-flex text-white bg-light mb-3 flex-nowrap" style="width: 20rem;">
  <div class="bg-secondary border">Flex item1</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
</div>

<div class="d-flex text-white bg-light mb-3 flex-wrap" style="width: 20rem;">
  <div class="bg-secondary border">Flex item1</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
</div>

<div class="d-flex text-white bg-light mb-3 flex-wrap-reverse" style="width: 20rem;">
  <div class="bg-secondary border">Flex item1</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
  <div class="bg-secondary border">Flex item</div>
</div>
```

* 排序  
.order-0 ~ .order-12  

<div class="d-flex text-white bg-light">
  <div class="order-3 p-2 bg-secondary border">First flex item</div>
  <div class="order-2 p-2 bg-secondary border">Second flex item</div>
  <div class="order-1 p-2 bg-secondary border">Third flex item</div>
</div>

* 垂直對齊  
.align-content-xx + flex-wrap 將物件對其於垂直位置  
使用於單列 flex 無作用  
> .align-content-start  
	.align-content-end  
	.align-content-center  
	.align-content-around  
	.align-content-stretch  
	.align-content-between

<div class="d-flex align-content-start text-white bg-light mb-3 flex-wrap" style="width: 20rem; height: 200px">
  <div class="p-2 bg-secondary border">Flex item1</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
</div>

<div class="d-flex align-content-center text-white bg-light mb-3 flex-wrap" style="width: 20rem; height: 200px">
  <div class="p-2 bg-secondary border">Flex item1</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
</div>

<div class="d-flex align-content-between text-white bg-light mb-3 flex-wrap" style="width: 20rem; height: 200px">
  <div class="p-2 bg-secondary border">Flex item1</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
</div>

<div class="d-flex align-content-around text-white bg-light mb-3 flex-wrap" style="width: 20rem; height: 200px">
  <div class="p-2 bg-secondary border">Flex item1</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
</div>

```html
<div class="d-flex align-content-start text-white bg-light mb-3 flex-wrap" style="width: 20rem; height: 200px">
  <div class="p-2 bg-secondary border">Flex item1</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
</div>

<div class="d-flex align-content-center text-white bg-light mb-3 flex-wrap" style="width: 20rem; height: 200px">
  <div class="p-2 bg-secondary border">Flex item1</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
</div>

<div class="d-flex align-content-between text-white bg-light mb-3 flex-wrap" style="width: 20rem; height: 200px">
  <div class="p-2 bg-secondary border">Flex item1</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
</div>

<div class="d-flex align-content-around text-white bg-light mb-3 flex-wrap" style="width: 20rem; height: 200px">
  <div class="p-2 bg-secondary border">Flex item1</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
  <div class="p-2 bg-secondary border">Flex item</div>
</div>
```

<a id="Float"></a>
## Float-浮動 [[Home]](#)  

* Classes(類別)
用 class 切換 float  

<div class="float-left">Float left on all viewport sizes</div><br>
<div class="float-right">Float right on all viewport sizes</div><br>
<div class="float-none">Don't float on all viewport sizes</div>

```html

<div class="float-left">Float left on all viewport sizes</div><br>
<div class="float-right">Float right on all viewport sizes</div><br>
<div class="float-none">Don't float on all viewport sizes</div>
```

* Mixins  
使用 Sass mixin

```html
.element {
  @include float-left;
}
.another-element {
  @include float-right;
}
.one-more {
  @include float-none;
}
```

<a id="ImageReplacement"></a>
## ImageReplacement-圖像替換 [[Home]](#)  
使用 .text-hide 或 Sass mixin 隱藏一個元素的文字內容並替換成背景圖片  

```html
<h1 class="text-hide">Custom heading</h1>
```

```html
// Usage as a mixin
.heading {
  @include text-hide;
}
```

使用 .text-hide 來維持標籤的親和性及 SEO，但要使用 background-image 取代文字內容  
<h1 class="text-hide" style="background-image: url('flower.jpg'); width: 50px; height: 50px;">Bootstrap</h1>

```html
<h1 class="text-hide" style="background-image: url('flower.jpg'); width: 50px; height: 50px;">Bootstrap</h1>
```

<a id="Overflow"></a>
## Overflow [[Home]](#)  
.overflow-auto : 超過變視窗  
.overflow-hidden : 超過不顯示  
default : 超過顯示  　　

<div class="overflow-auto bg-light mb-3" style="max-width: 260px; max-height: 100px;">
    This is an example of using <code>.overflow-auto</code> on an element with set width and height dimensions. By design, this content will vertically scroll.
</div>

<div class="overflow-hidden bg-light mb-3" style="max-width: 260px; max-height: 100px;">
    This is an example of using <code>.overflow-auto</code> on an element with set width and height dimensions. By design, this content will vertically scroll.
</div>

<div class="bg-light mb-3" style="max-width: 260px; max-height: 100px;">
    This is an example of using <code>.overflow-auto</code> on an element with set width and height dimensions. By design, this content will vertically scroll.
</div>

```html
<div class="overflow-auto bg-light mb-3" style="max-width: 260px; max-height: 100px;">
    This is an example of using <code>.overflow-auto</code> on an element with set width and height dimensions. By design, this content will vertically scroll.
</div>

<div class="overflow-hidden bg-light mb-3" style="max-width: 260px; max-height: 100px;">
    This is an example of using <code>.overflow-auto</code> on an element with set width and height dimensions. By design, this content will vertically scroll.
</div>

<div class="bg-light mb-3" style="max-width: 260px; max-height: 100px;">
    This is an example of using <code>.overflow-auto</code> on an element with set width and height dimensions. By design, this content will vertically scroll.
</div>
```

<a id="Position"></a>
## Position [[Home]](#)  

* 通用屬性  
快速增加定位 Class 是可以用不包含響應式  

```html
<div class="position-static">...</div>
<div class="position-relative">...</div>
<div class="position-absolute">...</div>
<div class="position-fixed">...</div>
<div class="position-sticky">...</div>
```

* 固定在頂部

```html
<div class="fixed-top">...</div>
```

* 固定在底部

```html
<div class="fixed-bottom">...</div>
```

* 貼齊於頂端 (Sticky top)  
將一個元素置於可視區的頂部，從邊緣到邊緣，但僅在你滾動視窗經過它之後。.sticky-top 通用類別使用 CSS 的 position: sticky，它並沒有支援所有的瀏覽器。  

```html
<div class="sticky-top">...</div>
```

<a id="Shadows"></a>
## Shadows [[Home]](#)  
雖然在 Bootstrap 中預設禁用元件上的陰影，但可透過 $enable-shadows 啟用  
也可以使用 box-shadow 通用類別快速增加或移除陰影  

<div class="shadow-none p-3 mb-5 bg-light rounded">No shadow</div>
<div class="shadow-sm p-3 mb-5 bg-white rounded">Small shadow</div>
<div class="shadow p-3 mb-5 bg-white rounded">Regular shadow</div>
<div class="shadow-lg p-3 mb-5 bg-white rounded">Larger shadow</div>

```html
<div class="shadow-none p-3 mb-5 bg-light rounded">No shadow</div>
<div class="shadow-sm p-3 mb-5 bg-white rounded">Small shadow</div>
<div class="shadow p-3 mb-5 bg-white rounded">Regular shadow</div>
<div class="shadow-lg p-3 mb-5 bg-white rounded">Larger shadow</div>
```

<a id="Sizing"></a>
## Sizing [[Home]](#)  

* 相對於父元素  
使用寬度和高度通用類別，可將一個元素加寬或增高  
相對於父元素寬度和高度通用類別預設包含 25%、 50%、 75% 和 100% 以及 auto 做為預設  

<div class="w-25 p-3 bg-light">Width 25%</div>
<div class="w-50 p-3 bg-light">Width 50%</div>
<div class="w-75 p-3 bg-light">Width 75%</div>
<div class="w-100 p-3 bg-light">Width 100%</div>
<div class="w-auto p-3 bg-light">Width auto</div>
<br>

```html
<div class="w-25 p-3 bg-light">Width 25%</div>
<div class="w-50 p-3 bg-light">Width 50%</div>
<div class="w-75 p-3 bg-light">Width 75%</div>
<div class="w-100 p-3 bg-light">Width 100%</div>
<div class="w-auto p-3 bg-light">Width auto</div>
```

<div style="height: 100px; background-color: rgba(255,0,0,0.1);">
  <div class="h-25 d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Height 25%</div>
  <div class="h-50 d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Height 50%</div>
  <div class="h-75 d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Height 75%</div>
  <div class="h-100 d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Height 100%</div>
  <div class="h-auto d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Height auto</div>
</div>
<br>

```html
<div style="height: 100px; background-color: rgba(255,0,0,0.1);">
  <div class="h-25 d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Height 25%</div>
  <div class="h-50 d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Height 50%</div>
  <div class="h-75 d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Height 75%</div>
  <div class="h-100 d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Height 100%</div>
  <div class="h-auto d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Height auto</div>
</div>
```

* 相對於視窗
使用通用類別來設定相對於視窗的寬度和高度

```html
<div class="min-vw-100">Min-width 100vw</div>
<div class="min-vh-100">Min-height 100vh</div>
<div class="vw-100">Width 100vw</div>
<div class="vh-100">Height 100vh</div>
```

<a id="Text"></a>
## Text-文字 [[Home]](#)  

* 文字對齊  
對於左、右、和置中對齊，可以使用響應式的 Class，使用與網格系統相同的 viewport 與中斷點  

<p class="text-left">Left aligned text on all viewport sizes.</p>
<p class="text-center">Center aligned text on all viewport sizes.</p>
<p class="text-right">Right aligned text on all viewport sizes.</p>

<p class="text-sm-left">Left aligned text on viewports sized SM (small) or wider.</p>
<p class="text-md-left">Left aligned text on viewports sized MD (medium) or wider.</p>
<p class="text-lg-left">Left aligned text on viewports sized LG (large) or wider.</p>
<p class="text-xl-left">Left aligned text on viewports sized XL (extra-large) or wider.</p>

```html
<p class="text-left">Left aligned text on all viewport sizes.</p>
<p class="text-center">Center aligned text on all viewport sizes.</p>
<p class="text-right">Right aligned text on all viewport sizes.</p>

<p class="text-sm-left">Left aligned text on viewports sized SM (small) or wider.</p>
<p class="text-md-left">Left aligned text on viewports sized MD (medium) or wider.</p>
<p class="text-lg-left">Left aligned text on viewports sized LG (large) or wider.</p>
<p class="text-xl-left">Left aligned text on viewports sized XL (extra-large) or wider.</p>
```

* text-wrap
防止換行可搭配 .text-nowrap  

<div class="text-nowrap bg-light mb-3">
Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. Donec pede justo, fringilla vel, aliquet nec, vulputate
</div>

<div class="bg-light mb-3">
Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. Donec pede justo, fringilla vel, aliquet nec, vulputate
</div>

```html
<div class="text-nowrap bg-light mb-3">
Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. Donec pede justo, fringilla vel, aliquet nec, vulputate
</div>

<div class="bg-light mb-3">
Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. Donec pede justo, fringilla vel, aliquet nec, vulputate
</div>
```

* 截掉多餘內容  
.text-truncate，可以截掉多餘內容改用 ...  
需要使用 display: inline-block or display: block  

<!-- Block level -->
<div class="row">
  <div class="col-2 text-truncate">
    Praeterea iter est quasdam res quas ex communi.
  </div>
</div>

<!-- Inline level -->
<span class="d-inline-block text-truncate" style="max-width: 150px;">
  Praeterea iter est quasdam res quas ex communi.
</span>

```html
.text-truncate，可以截掉多餘內容改用 ...。需要使用 display: inline-block or display: block  

<!-- Block level -->
<div class="row">
  <div class="col-2 text-truncate">
    Praeterea iter est quasdam res quas ex communi.
  </div>
</div>

<!-- Inline level -->
<span class="d-inline-block text-truncate" style="max-width: 150px;">
  Praeterea iter est quasdam res quas ex communi.
</span>
```

* 字體粗細和斜體  
> .font-weight-bold  
	.font-weight-bolder  
	.font-weight-normal  
	.font-weight-light  
	.font-weight-lighter  
	.font-italic  

<p class="font-weight-bold">Bold text.</p>
<p class="font-weight-bolder">Bolder weight text (relative to the parent element).</p>
<p class="font-weight-normal">Normal weight text.</p>
<p class="font-weight-light">Light weight text.</p>
<p class="font-weight-lighter">Lighter weight text (relative to the parent element).</p>
<p class="font-italic">Italic text.</p>

```html
<p class="font-weight-bold">Bold text.</p>
<p class="font-weight-bolder">Bolder weight text (relative to the parent element).</p>
<p class="font-weight-normal">Normal weight text.</p>
<p class="font-weight-light">Light weight text.</p>
<p class="font-weight-lighter">Lighter weight text (relative to the parent element).</p>
<p class="font-italic">Italic text.</p>
```

* Monospace(等寬字型)  
.text-monospace 來更換選擇 monospace 字體

<p class="text-monospace">This is in monospace</p>

```html
<p class="text-monospace">This is in monospace</p>
```

* Reset color
.text-reset 重設文字或連結的顏色，以便繼承父元素顏色  

<p class="text-muted">
  Muted text with a <a href="#" class="text-reset">reset link</a>.
</p>

```html
<p class="text-muted">
  Muted text with a <a href="#" class="text-reset">reset link</a>.
</p
```

<a id="VerticalAlignment"></a>
## VerticalAlignment-垂直對齊 [[Home]](#)  
改變 inline、inline-block、inline-table、和 table 元素的垂直對齊  

* 搭配 inline 元素

<span class="align-baseline">baseline</span>
<span class="align-top">top</span>
<span class="align-middle">middle</span>
<span class="align-bottom">bottom</span>
<span class="align-text-top">text-top</span>
<span class="align-text-bottom">text-bottom</span>

```html
<span class="align-baseline">baseline</span>
<span class="align-top">top</span>
<span class="align-middle">middle</span>
<span class="align-bottom">bottom</span>
<span class="align-text-top">text-top</span>
<span class="align-text-bottom">text-bottom</span>
```

* Table Cell

<div>
	<table style="height: 100px;">
	  <tbody>
	    <tr>
	      <td class="align-baseline">baseline</td>
	      <td class="align-top">top</td>
	      <td class="align-middle">middle</td>
	      <td class="align-bottom">bottom</td>
	      <td class="align-text-top">text-top</td>
	      <td class="align-text-bottom">text-bottom</td>
	    </tr>
	  </tbody>
	</table>
</div>

[bootstrap4_example](bootstrap4_example.html)-Table Cell
```html
<div>
	<table style="height: 100px;">
	  <tbody>
	    <tr>
	      <td class="align-baseline">baseline</td>
	      <td class="align-top">top</td>
	      <td class="align-middle">middle</td>
	      <td class="align-bottom">bottom</td>
	      <td class="align-text-top">text-top</td>
	      <td class="align-text-bottom">text-bottom</td>
	    </tr>
	  </tbody>
	</table>
</div>
```

<a id="Visibility"></a>
## Visibility-可見性 [[Home]](#)  
.invisible 元素仍會佔用頁面空間  
依需求使用 .visible 或 .invisible

```html 
<div class="visible">...</div>
<div class="invisible">...</div>
```

```html
// Class
.visible {
  visibility: visible;
}
.invisible {
  visibility: hidden;
}

// Usage as a mixin
.element {
  @include invisible(visible);
}
.element {
  @include invisible(hidden);
}
```