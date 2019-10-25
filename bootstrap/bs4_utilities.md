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

* Border  

<span class="border border-danger board-block"></span>
<span class="border-top border-danger board-block"></span>
<span class="border-right border-danger board-block"></span>
<span class="border-bottom border-danger board-block"></span>
<span class="border-left border-danger board-block"></span>

```html
<span class="border"></span>
<span class="border-top"></span>
<span class="border-right"></span>
<span class="border-bottom"></span>
<span class="border-left"></span>
```