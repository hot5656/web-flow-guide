## [Bootstrap 4 Guide](./bootstrap4_guide.md)
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<meta http-equiv="X-UA-Compatible" content="ie=edge">
	<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
	<title>Bootstrap 4.3.1</title>
</head>
<body>

<!-- Optional JavaScript -->
<!-- jQuery first, then Popper.js, then Bootstrap JS -->
<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
</body>
</html>

## BS4 components
* [Navbar](#navbar)
* [Navs](#navs)

<a id="navbar"></a>
## Navbar [[Home]](#) 

* base descript  

```html
# .navbar
# .navbar_expand{-sm|-md|-lg|-xl} : 若小於指定則為變更為 "折疊漢堡" 顯示menu項目
# fluid by default
# 使用 <nav> 元素確保親和性，或者如果使用更通用的元素 或 <div>，在導覽列中添加一個 role="navigation"
# ----------
# .navbar-brand : 為公司，產品或專案名稱
# .navbar-nav : 提供完整的高和輕便的導航（包括對下拉清單的支持）
# .navbar-toggler : 用於我們的折疊插件和其他
# .form-inline : 用於任何表單控制元件和操作
# .navbar-text : 用於垂直居中的文本字串
# .collapse.navbar-collapse : 用於外層中斷點群組和隱藏導覽列內容
```

* Brand  

<nav class="navbar navbar-light bg-light mb-2">
	<a class="navbar-brand" href="#">Brand</a>
</nav>

<nav class="navbar navbar-light bg-light mb-2">
	<a class="navbar-brand" href="#">
		<img src="flower.jpg" width="30" height="30" alt="">
	</a>
</nav>

<nav class="navbar navbar-light bg-light mb-2">
	<a class="navbar-brand" href="#">
		<img src="flower.jpg" width="30" height="30" alt="">
		Brand
	</a>
</nav>

<nav class="navbar navbar-light bg-light mb-2">
	<span class="navbar-brand mb-0 h1">Brand</span>
</nav>

```html
<!-- As a link -->
<nav class="navbar navbar-light bg-light">
	<a class="navbar-brand" href="#">Brand</a>
</nav>
<!-- As a link(image) -->
<nav class="navbar navbar-light bg-light">
	<a class="navbar-brand" href="#">
		<img src="flower.jpg" width="30" height="30" alt="">
	</a>
</nav>
<!-- As a link(image+text) -->
<nav class="navbar navbar-light bg-light">
	<a class="navbar-brand" href="#">
		<img src="flower.jpg" width="30" height="30" alt="">
		Brand
	</a>
</nav>
<!-- As a heading -->
<nav class="navbar navbar-light bg-light">
	<span class="navbar-brand mb-0 h1">Brand</span>
</nav>
```

* Navbar 折疊漢堡  

<!-- lg 以下變為摺疊漢堡 -->
<nav class="navbar navbar-expand-lg navbar-light bg-light mb-2">
	<!-- brand -->
	<a class="navbar-brand" href="#">Navbar</a>
	<!-- class="navbar-toggler" : 摺疊漢堡 button															-->
	<!-- data-target="#navbarNav" aria-controls="navbarNav" : control map id 	-->
	<!-- data-toggle="collapse" : 觸發 collapse 															-->
	<!-- aria-expanded="false" : 觸發開關 default off 												-->
	<!-- aria-label="Toggle navigation" : 提供閱讀障礙使用者參考							-->
	<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
		<!-- set icon -->
		<span class="navbar-toggler-icon"></span>
	</button>
	<!-- collapse navbar-collapse 指定隱藏內容 -->
	<!-- navbarNav 對應摺疊漢堡 button 之 id -->
	<div class="collapse navbar-collapse" id="navbarNav">
		<ul class="navbar-nav">
			<li class="nav-item active">
				<a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
			</li>
			<li class="nav-item">
				<a class="nav-link" href="#">Features</a>
			</li>
			<li class="nav-item">
				<a class="nav-link" href="#">Pricing</a>
			</li>
			<li class="nav-item">
				<a class="nav-link disabled" href="#">Disabled</a>
			</li>
		</ul>
	</div>
</nav>

<!-- lg 以下變為摺疊漢堡 - remove ul-li -->
<nav class="navbar navbar-expand-lg navbar-light bg-light mb-2">
	<!-- brand -->
	<a class="navbar-brand" href="#">Navbar</a>
	<!-- class="navbar-toggler" : 摺疊漢堡 button															-->
	<!-- data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" : control map id 	-->
	<!-- data-toggle="collapse" : 觸發 collapse 															-->
	<!-- aria-expanded="false" : 觸發開關 default off 												-->
	<!-- aria-label="Toggle navigation" : 提供閱讀障礙使用者參考							-->
	<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
		<!-- set icon -->
		<span class="navbar-toggler-icon"></span>
	</button>
	<!-- collapse navbar-collapse 指定隱藏內容 -->
	<!-- navbarNavAltMarkup 對應摺疊漢堡 button 之 id -->
	<div class="collapse navbar-collapse" id="navbarNavAltMarkup">
		<div class="navbar-nav">
			<a class="nav-item nav-link active" href="#">Home <span class="sr-only">(current)</span></a>
			<a class="nav-item nav-link" href="#">Features</a>
			<a class="nav-item nav-link" href="#">Pricing</a>
			<a class="nav-item nav-link disabled" href="#">Disabled</a>
		</div>
	</div>
</nav>

<nav class="navbar navbar-expand-lg navbar-light bg-light mb-2">
	<a class="navbar-brand" href="#">Navbar</a>
	<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
		<span class="navbar-toggler-icon"></span>
	</button>
	<div class="collapse navbar-collapse" id="navbarNavDropdown">
		<ul class="navbar-nav">
			<li class="nav-item active">
				<a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
			</li>
			<li class="nav-item">
				<a class="nav-link" href="#">Features</a>
			</li>
			<li class="nav-item">
				<a class="nav-link" href="#">Pricing</a>
			</li>
			<li class="nav-item dropdown">
				<a class="nav-link dropdown-toggle" href="#" id="navbarDropdownMenuLink" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
					Dropdown link
				</a>
				<div class="dropdown-menu" aria-labelledby="navbarDropdownMenuLink">
					<a class="dropdown-item" href="#">Action</a>
					<a class="dropdown-item" href="#">Another action</a>
					<a class="dropdown-item" href="#">Something else here</a>
				</div>
			</li>
		</ul>
	</div>
</nav>


```html
<!-- lg 以下變為摺疊漢堡 -->
<nav class="navbar navbar-expand-lg navbar-light bg-light">
	<!-- brand -->
	<a class="navbar-brand" href="#">Navbar</a>
	<!-- class="navbar-toggler" : 摺疊漢堡 button															-->
	<!-- data-target="#navbarNav" aria-controls="navbarNav" : control map id 	-->
	<!-- data-toggle="collapse" : 觸發 collapse 															-->
	<!-- aria-expanded="false" : 觸發開關 default off 												-->
	<!-- aria-label="Toggle navigation" : 提供閱讀障礙使用者參考							-->
	<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
		<!-- set icon -->
		<span class="navbar-toggler-icon"></span>
	</button>
	<!-- collapse navbar-collapse 指定隱藏內容 -->
	<!-- navbarNav 對應摺疊漢堡 button 之 id -->
	<div class="collapse navbar-collapse" id="navbarNav">
		<ul class="navbar-nav">
			<li class="nav-item active">
				<a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
			</li>
			<li class="nav-item">
				<a class="nav-link" href="#">Features</a>
			</li>
			<li class="nav-item">
				<a class="nav-link" href="#">Pricing</a>
			</li>
			<li class="nav-item">
				<a class="nav-link disabled" href="#">Disabled</a>
			</li>
		</ul>
	</div>
</nav>
<!-- lg 以下變為摺疊漢堡 - remove ul-li -->
<nav class="navbar navbar-expand-lg navbar-light bg-light mb-2">
	<!-- brand -->
	<a class="navbar-brand" href="#">Navbar</a>
	<!-- class="navbar-toggler" : 摺疊漢堡 button															-->
	<!-- data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" : control map id 	-->
	<!-- data-toggle="collapse" : 觸發 collapse 															-->
	<!-- aria-expanded="false" : 觸發開關 default off 												-->
	<!-- aria-label="Toggle navigation" : 提供閱讀障礙使用者參考							-->
	<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
		<!-- set icon -->
		<span class="navbar-toggler-icon"></span>
	</button>
	<!-- collapse navbar-collapse 指定隱藏內容 -->
	<!-- navbarNavAltMarkup 對應摺疊漢堡 button 之 id -->
	<div class="collapse navbar-collapse" id="navbarNavAltMarkup">
		<div class="navbar-nav">
			<a class="nav-item nav-link active" href="#">Home <span class="sr-only">(current)</span></a>
			<a class="nav-item nav-link" href="#">Features</a>
			<a class="nav-item nav-link" href="#">Pricing</a>
			<a class="nav-item nav-link disabled" href="#">Disabled</a>
		</div>
	</div>
</nav>
<!-- lg 以下變為摺疊漢堡 - add dropdown menus -->
<nav class="navbar navbar-expand-lg navbar-light bg-light mb-2">
	<!-- brand -->
	<a class="navbar-brand" href="#">Navbar</a>
	<!-- class="navbar-toggler" : 摺疊漢堡 button															-->
	<!-- data-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" : control map id 	-->
	<!-- data-toggle="collapse" : 觸發 collapse 															-->
	<!-- aria-expanded="false" : 觸發開關 default off 												-->
	<!-- aria-label="Toggle navigation" : 提供閱讀障礙使用者參考							-->
	<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
		<!-- set icon -->
		<span class="navbar-toggler-icon"></span>
	</button>
	<!-- collapse navbar-collapse 指定隱藏內容 -->
	<!-- navbarNavDropdown 對應摺疊漢堡 button 之 id -->
	<div class="collapse navbar-collapse" id="navbarNavDropdown">
		<ul class="navbar-nav">
			<li class="nav-item active">
				<a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
			</li>
			<li class="nav-item">
				<a class="nav-link" href="#">Features</a>
			</li>
			<li class="nav-item">
				<a class="nav-link" href="#">Pricing</a>
			</li>
			<li class="nav-item dropdown">
				<a class="nav-link dropdown-toggle" href="#" id="navbarDropdownMenuLink" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
					Dropdown link
				</a>
				<div class="dropdown-menu" aria-labelledby="navbarDropdownMenuLink">
					<a class="dropdown-item" href="#">Action</a>
					<a class="dropdown-item" href="#">Another action</a>
					<a class="dropdown-item" href="#">Something else here</a>
				</div>
			</li>
		</ul>
	</div>
</nav>
```


<a id="navs"></a>
## Navs [[Home]](#) 
<div class="alert alert-warning" role="alert">
	<p>tabindex="-1" : tab 切換時會排除在外</p>
	<p>aria-disabled="true" : 指出表單區域是處於停用的狀態</p>
</div>
* Base  
<nav class="nav">
	<a class="nav-link active" href="#">Active</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>

<nav class="nav justify-content-center">
	<a class="nav-link active" href="#">Active</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>

<nav class="nav justify-content-end">
	<a class="nav-link active" href="#">Active</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>

```html
<!-- left(default) -->
<nav class="nav">
	<a class="nav-link active" href="#">Active</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>
<!-- center(justify-content-center) -->
<nav class="nav justify-content-center">
	<a class="nav-link active" href="#">Active</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>
<!-- right(justify-content-end) -->
<nav class="nav justify-content-end">
	<a class="nav-link active" href="#">Active</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>
```

* Vertical - flex-column  
<nav class="nav flex-column">
	<a class="nav-link active" href="#">Active</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>

```html
<nav class="nav flex-column">
	<a class="nav-link active" href="#">Active</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>
```

* Tabs - nav-tabs  
<nav class="nav nav-tabs">
	<a class="nav-link active" href="#">Active</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>

```html
<nav class="nav nav-tabs">
	<a class="nav-link active" href="#">Active</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>
```

* Pills - nav-pills  
<nav class="nav nav-pills">
	<a class="nav-link active" href="#">Active</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>

<nav class="nav nav-pills nav-fill">
	<a class="nav-item nav-link active" href="#">Active</a>
	<a class="nav-item nav-link" href="#">Much longer nav link</a>
	<a class="nav-item nav-link" href="#">Link</a>
	<a class="nav-item nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>

<nav class="nav nav-pills nav-justified">
	<a class="nav-item nav-link active" href="#">Active</a>
	<a class="nav-item nav-link" href="#">Much longer nav link</a>
	<a class="nav-item nav-link" href="#">Link</a>
	<a class="nav-item nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>

```html
<!-- default -->
<nav class="nav nav-pills">
	<a class="nav-link active" href="#">Active</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>
<!-- space(nav-fill+nav-item) -->
<nav class="nav nav-pills nav-fill">
	<a class="nav-item nav-link active" href="#">Active</a>
	<a class="nav-item nav-link" href="#">Much longer nav link</a>
	<a class="nav-item nav-link" href="#">Link</a>
	<a class="nav-item nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>
<!-- same item wide(nav-justified+nav-item) -->
<nav class="nav nav-pills nav-justified">
	<a class="nav-item nav-link active" href="#">Active</a>
	<a class="nav-item nav-link" href="#">Much longer nav link</a>
	<a class="nav-item nav-link" href="#">Link</a>
	<a class="nav-item nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>
```

* flex aligment  

<div class="alert alert-info" role="alert">
	Don't check detail
</div>

<nav class="nav nav-pills flex-column flex-sm-row">
	<a class="flex-sm-fill text-sm-center nav-link active" href="#">Active</a>
	<a class="flex-sm-fill text-sm-center nav-link" href="#">Longer nav link</a>
	<a class="flex-sm-fill text-sm-center nav-link" href="#">Link</a>
	<a class="flex-sm-fill text-sm-center nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>

```html
<nav class="nav nav-pills flex-column flex-sm-row">
	<a class="flex-sm-fill text-sm-center nav-link active" href="#">Active</a>
	<a class="flex-sm-fill text-sm-center nav-link" href="#">Longer nav link</a>
	<a class="flex-sm-fill text-sm-center nav-link" href="#">Link</a>
	<a class="flex-sm-fill text-sm-center nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>
```