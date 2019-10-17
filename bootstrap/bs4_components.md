## [Bootstrap 4 Guide](./bootstrap4_guide.md)
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<meta http-equiv="X-UA-Compatible" content="ie=edge">
	<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
	<title>BS4 components</title>
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
* [Navbar-導覽列](#navbar)
* [Navs-導覽](#navs)
* [Card-卡片](#Card)
* [List](#List)

<a id="navbar"></a>
## Navbar [[Home]](#) 

* base descript  

```html
# .navbar
# .navbar_expand{-sm|-md|-lg|-xl} : 若小於指定則為變更為 "折疊漢堡" 顯示menu項目
# fluid by default
# 使用 <nav> 元素確保親和性，或者如果使用更通用的元素 或 <div>，在導覽列中添加一個 role="navigation"
# 對於不需要折疊的導覽列，在導覽列中加入 .navbar-expand
# 對於總是折疊的導覽列，不要加任何 .navbar-expand class。
# ----------
# .navbar-brand : 為公司，產品或專案名稱
# .navbar-nav : 提供完整的高和輕便的導航（包括對下拉清單的支持）
# .navbar-toggler : 用於我們的折疊插件和其他
# .form-inline : 用於任何表單控制元件和操作
# .navbar-text : 用於垂直居中的文本字串
# .collapse.navbar-collapse : 用於外層中斷點群組和隱藏導覽列內容
```

* Brand  
	* Text
	<nav class="navbar navbar-light bg-light">
		<a class="navbar-brand" href="#">Brand</a>
	</nav>

	* Image
	<nav class="navbar navbar-light bg-light">
		<a class="navbar-brand" href="#">
			<img src="flower.jpg" width="30" height="30" alt="">
		</a>
	</nav>

	* Image+Text
	<nav class="navbar navbar-light bg-light">
		<a class="navbar-brand" href="#">
			<img src="flower.jpg" width="30" height="30" alt="">
			Brand
		</a>
	</nav>

	* Not link 
	<nav class="navbar navbar-light bg-light">
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
	*	basic
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

	[bootstrap4_example](bootstrap4_example.html)-NavbarBase

	* remove ui-li
	<!-- lg 以下變為摺疊漢堡 - remove ul-li -->
	<nav class="navbar navbar-expand-lg navbar-light bg-light">
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

	* add dropdown menus
	<!-- lg 以下變為摺疊漢堡 - add dropdown menus -->
	<nav class="navbar navbar-expand-lg navbar-light bg-light">
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

	[bootstrap4_example](bootstrap4_example.html)-NavbarDropdown

	* default 摺疊  
	<!-- default 摺疊 - no add navbar-expand-xx -->
	<nav class="navbar navbar-dark bg-dark">
	  <div class="collapse navbar-collapse" id="navbarTogglerDemo04">
	      <h5 class="text-white h4">Collapsed content</h5>
	      <span class="text-muted">Toggleable via the navbar brand.</span>
	  </div>
	  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarTogglerDemo04" aria-controls="navbarTogglerDemo04" aria-expanded="false" aria-label="Toggle navigation">
	    <span class="navbar-toggler-icon"></span>
	  </button>
	</nav>

	[bootstrap4_example](bootstrap4_example.html)-NavbarClose


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
<nav class="navbar navbar-expand-lg navbar-light bg-light">
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
<nav class="navbar navbar-expand-lg navbar-light bg-light">
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
			<!-- navbarDropdownMenuLink : dropdowm map id -->
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
<!-- default 摺疊 - no add navbar-expand-xx -->
<nav class="navbar navbar-dark bg-dark">
  <div class="collapse navbar-collapse" id="navbarTogglerDemo04">
      <h5 class="text-white h4">Collapsed content</h5>
      <span class="text-muted">Toggleable via the navbar brand.</span>
  </div>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarTogglerDemo04" aria-controls="navbarTogglerDemo04" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
</nav>
```

* Form  
	* Search  
	<nav class="navbar navbar-light bg-light">
	  <form class="form-inline">
	    <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
	    <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
	  </form>
	</nav>

	* button  
	<nav class="navbar navbar-light bg-light">
	  <form class="form-inline">
	    <button class="btn btn-outline-success" type="button">Main button</button>
	    <button class="btn btn-sm btn-outline-secondary" type="button">Smaller button</button>
	  </form>
	</nav>

```html
<-- Search -->
<nav class="navbar navbar-light bg-light">
	 <form class="form-inline">
	   <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
	   <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
	 </form>
</nav>
<-- button -->
<nav class="navbar navbar-light bg-light">
	 <form class="form-inline">
	   <button class="btn btn-outline-success" type="button">Main button</button>
	   <button class="btn btn-sm btn-outline-secondary" type="button">Smaller button</button>
	 </form>
</nav>
```

* Text  
<nav class="navbar navbar-light bg-light">
  <span class="navbar-text">
    Navbar text with an inline element
  </span>
</nav>

```html
<nav class="navbar navbar-light bg-light">
  <span class="navbar-text">
    Navbar text with an inline element
  </span>
</nav>
```

* Color  
	<nav class="navbar navbar-dark bg-dark">
		<span class="navbar-brand mb-0 h1">Brand</span>
		<a class="nav-link active" href="#">Home</a>
		<a class="nav-link" href="#">Features</a>
		<a class="nav-link" href="#">About</a>
	</nav><br>
	<!-- -->
	<nav class="navbar navbar-dark bg-primary">
		<span class="navbar-brand mb-0 h1">Brand</span>
		<a class="nav-link active" href="#">Home</a>
		<a class="nav-link" href="#">Features</a>
		<a class="nav-link" href="#">About</a>
	</nav><br>
	<!-- -->
	<nav class="navbar navbar-light" style="background-color: #e3f2fd;"">
		<span class="navbar-brand mb-0 h1">Brand</span>
		<a class="nav-link active" href="#">Home</a>
		<a class="nav-link" href="#">Features</a>
		<a class="nav-link" href="#">About</a>
	</nav><br>

```html
<!-- bg-dark -->
<nav class="navbar navbar-dark bg-dark">
	<span class="navbar-brand mb-0 h1">Brand</span>
	<a class="nav-link active" href="#">Home</a>
	<a class="nav-link" href="#">Features</a>
	<a class="nav-link" href="#">About</a>
</nav><br>
<!-- bg-dark/pick bg-color -->
<nav class="navbar navbar-dark bg-primary">
	<span class="navbar-brand mb-0 h1">Brand</span>
	<a class="nav-link active" href="#">Home</a>
	<a class="nav-link" href="#">Features</a>
	<a class="nav-link" href="#">About</a>
</nav><br>
<!-- bg-loght/pick bg-color -->
<nav class="navbar navbar-light" style="background-color: #e3f2fd;"">
	<span class="navbar-brand mb-0 h1">Brand</span>
	<a class="nav-link active" href="#">Home</a>
	<a class="nav-link" href="#">Features</a>
	<a class="nav-link" href="#">About</a>
</nav><br>
```

* Navbar 折疊漢堡 brand 位置  
	* brand 隱藏  
	<!-- brand 隱藏 -->
	<nav class="navbar navbar-expand-lg navbar-light bg-light">
		<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
			<span class="navbar-toggler-icon"></span>
		</button>
		<div class="collapse navbar-collapse" id="navbarNavAltMarkup">
			<!-- brand -->
			<a class="navbar-brand" href="#">Navbar</a>
			<div class="navbar-nav">
				<a class="nav-item nav-link active" href="#">Home <span class="sr-only">(current)</span></a>
				<a class="nav-item nav-link" href="#">Features</a>
				<a class="nav-item nav-link" href="#">Pricing</a>
				<a class="nav-item nav-link disabled" href="#">Disabled</a>
			</div>
		</div>
	</nav>

	* brand 置於左邊  
	<!-- brand 置於左邊 -->
	<nav class="navbar navbar-expand-lg navbar-light bg-light">
		<!-- brand -->
		<a class="navbar-brand" href="#">Navbar</a>
		<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
			<span class="navbar-toggler-icon"></span>
		</button>
		<div class="collapse navbar-collapse" id="navbarNavAltMarkup">
			<div class="navbar-nav">
				<a class="nav-item nav-link active" href="#">Home <span class="sr-only">(current)</span></a>
				<a class="nav-item nav-link" href="#">Features</a>
				<a class="nav-item nav-link" href="#">Pricing</a>
				<a class="nav-item nav-link disabled" href="#">Disabled</a>
			</div>
		</div>
	</nav>

	* brand 置於右變  
	<!-- brand 置於右變 -->
	<nav class="navbar navbar-expand-lg navbar-light bg-light">
		<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
			<span class="navbar-toggler-icon"></span>
		</button>
		<!-- brand -->
		<a class="navbar-brand" href="#">Navbar</a>
		<div class="collapse navbar-collapse" id="navbarNavAltMarkup">
			<div class="navbar-nav">
				<a class="nav-item nav-link active" href="#">Home <span class="sr-only">(current)</span></a>
				<a class="nav-item nav-link" href="#">Features</a>
				<a class="nav-item nav-link" href="#">Pricing</a>
				<a class="nav-item nav-link disabled" href="#">Disabled</a>
			</div>
		</div>
	</nav>

```html
<!-- brand 隱藏 -->
<nav class="navbar navbar-expand-lg navbar-light bg-light">
	<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
		<span class="navbar-toggler-icon"></span>
	</button>
	<div class="collapse navbar-collapse" id="navbarNavAltMarkup">
		<!-- brand -->
		<a class="navbar-brand" href="#">Navbar</a>
		<div class="navbar-nav">
			<a class="nav-item nav-link active" href="#">Home <span class="sr-only">(current)</span></a>
			<a class="nav-item nav-link" href="#">Features</a>
			<a class="nav-item nav-link" href="#">Pricing</a>
			<a class="nav-item nav-link disabled" href="#">Disabled</a>
		</div>
	</div>
</nav>
<!-- brand 置於左邊 -->
<nav class="navbar navbar-expand-lg navbar-light bg-light">
	<!-- brand -->
	<a class="navbar-brand" href="#">Navbar</a>
	<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
		<span class="navbar-toggler-icon"></span>
	</button>
	<div class="collapse navbar-collapse" id="navbarNavAltMarkup">
		<div class="navbar-nav">
			<a class="nav-item nav-link active" href="#">Home <span class="sr-only">(current)</span></a>
			<a class="nav-item nav-link" href="#">Features</a>
			<a class="nav-item nav-link" href="#">Pricing</a>
			<a class="nav-item nav-link disabled" href="#">Disabled</a>
		</div>
	</div>
</nav>
<!-- brand 置於右變 -->
<nav class="navbar navbar-expand-lg navbar-light bg-light">
	<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
		<span class="navbar-toggler-icon"></span>
	</button>
	<!-- brand -->
	<a class="navbar-brand" href="#">Navbar</a>
	<div class="collapse navbar-collapse" id="navbarNavAltMarkup">
		<div class="navbar-nav">
			<a class="nav-item nav-link active" href="#">Home <span class="sr-only">(current)</span></a>
			<a class="nav-item nav-link" href="#">Features</a>
			<a class="nav-item nav-link" href="#">Pricing</a>
			<a class="nav-item nav-link disabled" href="#">Disabled</a>
		</div>
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
	* left(default)  
	<nav class="nav bg-light">
		<a class="nav-link active" href="#">Active</a>
		<a class="nav-link" href="#">Link</a>
		<a class="nav-link" href="#">Link</a>
		<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
	</nav>

	* center  
	<nav class="nav justify-content-center bg-light">
		<a class="nav-link active" href="#">Active</a>
		<a class="nav-link" href="#">Link</a>
		<a class="nav-link" href="#">Link</a>
		<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
	</nav>

	* right  
	<nav class="nav justify-content-end bg-light">
		<a class="nav-link active" href="#">Active</a>
		<a class="nav-link" href="#">Link</a>
		<a class="nav-link" href="#">Link</a>
		<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
	</nav>

```html
<!-- left(default) -->
<nav class="nav bg-light">
	<a class="nav-link active" href="#">Active</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>
<!-- center(justify-content-center) -->
<nav class="nav justify-content-center bg-light">
	<a class="nav-link active" href="#">Active</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>
<!-- right(justify-content-end) -->
<nav class="nav justify-content-end bg-light">
	<a class="nav-link active" href="#">Active</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>
```

* Vertical - flex-column  
<nav class="nav flex-column bg-light">
	<a class="nav-link active" href="#">Active</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link" href="#">Link</a>
	<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
</nav>

```html
<nav class="nav flex-column bg-light">
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
	* default  
	<nav class="nav nav-pills">
		<a class="nav-link active" href="#">Active</a>
		<a class="nav-link" href="#">Link</a>
		<a class="nav-link" href="#">Link</a>
		<a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
	</nav>

	* nav-fill  
	<nav class="nav nav-pills nav-fill">
		<a class="nav-item nav-link active" href="#">Active</a>
		<a class="nav-item nav-link" href="#">Much longer nav link</a>
		<a class="nav-item nav-link" href="#">Link</a>
		<a class="nav-item nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
	</nav>

	* nav-justified  
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

*  Dynamic tabbed(動態頁籤)  
	* Basic  
	<!-- Basic -->
	<!-- id="nav-home-tab"  to   aria-labelledby="nav-home-tab" -->
	<!-- href="#nav-home" to id="nav-home" -->
	<nav>
		<div class="nav nav-tabs" role="tablist">
			<a class="nav-item nav-link active" id="nav-home-tab" data-toggle="tab" href="#nav-home" role="tab" aria-controls="nav-home" aria-selected="true">Home</a>
			<a class="nav-item nav-link" id="nav-profile-tab" data-toggle="tab" href="#nav-profile" role="tab" aria-controls="nav-profile" aria-selected="false">Profile</a>
			<a class="nav-item nav-link" id="nav-contact-tab" data-toggle="tab" href="#nav-contact" role="tab" aria-controls="nav-contact" aria-selected="false">Contact</a>
		</div>
	</nav>
	<div class="tab-content">
		<div class="tab-pane fade show active" id="nav-home" role="tabpanel" aria-labelledby="nav-home-tab">home...</div>
		<div class="tab-pane fade" id="nav-profile" role="tabpanel" aria-labelledby="nav-profile-tab">profile...</div>
		<div class="tab-pane fade" id="nav-contact" role="tabpanel" aria-labelledby="nav-contact-tab">contact...</div>
	</div>

	[bootstrap4_example](bootstrap4_example.html)-NavDynamicTabbed

	* Vertical  
	<!-- Vertical -->
	<!-- id="nav-home-tab-v"  to   aria-labelledby="nav-home-tab-v" -->
	<!-- href="#nav-home-v" to id="nav-home-v" -->
	<!-- col-3, col-9 -->
	<div class="row">
		<div class="col-3">
			<div class="nav nav-pills flex-column"role="tablist">
				<a class="nav-item nav-link active" id="nav-home-tab-v" data-toggle="tab" href="#nav-home-v" role="tab" aria-controls="nav-home" aria-selected="true">Home</a>
					<a class="nav-item nav-link" id="nav-profile-tab-v" data-toggle="tab" href="#nav-profile-v" role="tab" aria-controls="nav-profile" aria-selected="false">Profile<a>
					<a class="nav-item nav-link" id="nav-contact-tab-v" data-toggle="tab" href="#nav-contact-v" role="tab" aria-controls="nav-contact" aria-selected="false">Contact<a>
			</div>
		</div>
		<div class="col-9">
			<div class="tab-content">
				<div class="tab-pane fade show active" id="nav-home-v" role="tabpanel" aria-labelledby="nav-home-tab-v">home Vertical...</div>
				<div class="tab-pane fade" id="nav-profile-v" role="tabpanel" aria-labelledby="nav-profile-tab-v">profile Vertical...</div>
				<div class="tab-pane fade" id="nav-contact-v" role="tabpanel" aria-labelledby="nav-contact-tab-v">contact Vertical...</div>
			</div>
		</div>
	</div>

	[bootstrap4_example](bootstrap4_example.html)-NavDynamicTabbedVertical

```html
<!-- Basic -->
<!-- id="nav-home-tab"  to   aria-labelledby="nav-home-tab" -->
<!-- href="#nav-home" to id="nav-home" -->
<nav>
	<div class="nav nav-tabs" role="tablist">
		<a class="nav-item nav-link active" id="nav-home-tab" data-toggle="tab" href="#nav-home" role="tab" aria-controls="nav-home" aria-selected="true">Home</a>
		<a class="nav-item nav-link" id="nav-profile-tab" data-toggle="tab" href="#nav-profile" role="tab" aria-controls="nav-profile" aria-selected="false">Profile</a>
		<a class="nav-item nav-link" id="nav-contact-tab" data-toggle="tab" href="#nav-contact" role="tab" aria-controls="nav-contact" aria-selected="false">Contact</a>
	</div>
</nav>
<div class="tab-content">
	<div class="tab-pane fade show active" id="nav-home" role="tabpanel" aria-labelledby="nav-home-tab">home...</div>
	<div class="tab-pane fade" id="nav-profile" role="tabpanel" aria-labelledby="nav-profile-tab">profile...</div>
	<div class="tab-pane fade" id="nav-contact" role="tabpanel" aria-labelledby="nav-contact-tab">contact...</div>
</div>
<!-- Vertical -->
<!-- id="nav-home-tab-v"  to   aria-labelledby="nav-home-tab-v" -->
<!-- href="#nav-home-v" to id="nav-home-v" -->
<!-- col-3, col-9 -->
<div class="row">
	<div class="col-3">
		<div class="nav nav-pills flex-column"role="tablist">
			<a class="nav-item nav-link active" id="nav-home-tab-v" data-toggle="tab" href="#nav-home-v" role="tab" aria-controls="nav-home" aria-selected="true">Home</a>
				<a class="nav-item nav-link" id="nav-profile-tab-v" data-toggle="tab" href="#nav-profile-v" role="tab" aria-controls="nav-profile" aria-selected="false">Profile<a>
				<a class="nav-item nav-link" id="nav-contact-tab-v" data-toggle="tab" href="#nav-contact-v" role="tab" aria-controls="nav-contact" aria-selected="false">Contact<a>
		</div>
	</div>
	<div class="col-9">
		<div class="tab-content">
			<div class="tab-pane fade show active" id="nav-home-v" role="tabpanel" aria-labelledby="nav-home-tab-v">home Vertical...</div>
			<div class="tab-pane fade" id="nav-profile-v" role="tabpanel" aria-labelledby="nav-profile-tab-v">profile Vertical...</div>
			<div class="tab-pane fade" id="nav-contact-v" role="tabpanel" aria-labelledby="nav-contact-tab-v">contact Vertical...</div>
		</div>
	</div>
</div>
```

<a id="Card"></a>
## Card [[Home]](#) 
```
card
card-img-top
card-title
card-subtitle 
card-text
card-header
card-body
card-footer 
```

* image head  

<div class="card" style="width: 18rem;">
  <img src="https://fakeimg.pl/250x100/" class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div><br>

```html
<div class="card" style="width: 18rem;">
  <img src="https://fakeimg.pl/250x100/" class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

* list  
<div class="card" style="width: 18rem;">
  <div class="card-header">
    Featured
  </div>
  <ul class="list-group list-group-flush">
    <li class="list-group-item">Cras justo odio</li>
    <li class="list-group-item">Dapibus ac facilisis in</li>
    <li class="list-group-item">Vestibulum at eros</li>
  </ul>
</div><br>

[bootstrap4_example](bootstrap4_example.html)-CarList

```html
<div class="card" style="width: 18rem;">
  <div class="card-header">
    Featured
  </div>
  <ul class="list-group list-group-flush">
    <li class="list-group-item">Cras justo odio</li>
    <li class="list-group-item">Dapibus ac facilisis in</li>
    <li class="list-group-item">Vestibulum at eros</li>
  </ul>
</div>
```

* header and footer  

<div class="card text-center">
	<div class="card-header">
		Featured
	</div>
	<div class="card-body">
		<h5 class="card-title">Special title treatment</h5>
		<p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
		<a href="#" class="btn btn-primary">Go somewhere</a>
	</div>
	<div class="card-footer text-muted">
		2 days ago
	</div>
</div><br>

```html
<div class="card text-center">
  <div class="card-header">
    Featured
  </div>
  <div class="card-body">
    <h5 class="card-title">Special title treatment</h5>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
  <div class="card-footer text-muted">
    2 days ago
  </div>
</div>
```

* Image overlays(圖像轉換為卡片背景)  

<div class="card bg-dark text-white">
  <img src="https://fakeimg.pl/400x200/" class="card-img-top" alt="...">
  <div class="card-img-overlay">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    <p class="card-text">Last updated 3 mins ago</p>
  </div>
</div><br>	

```html
<div class="card bg-dark text-white">
  <img src="https://fakeimg.pl/400x200/" class="card-img-top" alt="...">
  <div class="card-img-overlay">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    <p class="card-text">Last updated 3 mins ago</p>
  </div>
</div>
```

<a id="List"></a>
## List [[Home]](#) 
```
w-50 : 50% (see more good)
list-group
list-group-item
list-group-flush : 來移除部分邊框及圓角，用來產生邊緣貼齊的列表群組，這可用在一個容器內(如：卡片)
```

* Basic

<ul class="list-group w-50">
  <li class="list-group-item">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item">Vestibulum at eros</li>
</ul>

```html
<ul class="list-group w-50">
  <li class="list-group-item">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item">Vestibulum at eros</li>
</ul>
```

* Active

<ul class="list-group w-50">
  <li class="list-group-item active">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item">Vestibulum at eros</li>
</ul>

```html
<ul class="list-group w-50">
  <li class="list-group-item active">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item">Vestibulum at eros</li>
</ul>
```

* Disable

<ul class="list-group w-50">
  <li class="list-group-item disabled">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item">Vestibulum at eros</li>
</ul>

```html
<ul class="list-group w-50">
  <li class="list-group-item disabled">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item" tabindex="-1" aria-disabled="true">Vestibulum at eros</li>
</ul>
```

* a tag

<ul class="list-group w-50">
	<a href="#" class="list-group-item list-group-item-action">Cras justo odio</a>
	<a href="#" class="list-group-item list-group-item-action">Dapibus ac facilisis in</a>
	<a href="#" class="list-group-item list-group-item-action">Morbi leo risus</a>
	<a href="#" class="list-group-item list-group-item-action">Porta ac consectetur ac</a>
	<a href="#" class="list-group-item list-group-item-action">Vestibulum at eros disabled</a>
</ul>

```html
<ul class="list-group w-50">
	<a href="#" class="list-group-item list-group-item-action">Cras justo odio</a>
	<a href="#" class="list-group-item list-group-item-action">Dapibus ac facilisis in</a>
	<a href="#" class="list-group-item list-group-item-action">Morbi leo risus</a>
	<a href="#" class="list-group-item list-group-item-action">Porta ac consectetur ac</a>
	<a href="#" class="list-group-item list-group-item-action">Vestibulum at eros disabled</a>
</ul>
```

* button tag  
不能在這裡使用標準的 .btn  

<ul class="list-group w-50">
	<button type="button" class="list-group-item list-group-item-action">Cras justo odio</button>
	<button type="button" class="list-group-item list-group-item-action">Dapibus ac facilisis in</button>
	<button type="button" class="list-group-item list-group-item-action">Morbi leo risus</button>
	<button type="button" class="list-group-item list-group-item-action">Porta ac consectetur ac</button>
	<button type="button" class="list-group-item list-group-item-action" disabled>Vestibulum at eros disabled</button>
</ul>

```html
<ul class="list-group w-50">
	<button type="button" class="list-group-item list-group-item-action">Cras justo odio</button>
	<button type="button" class="list-group-item list-group-item-action">Dapibus ac facilisis in</button>
	<button type="button" class="list-group-item list-group-item-action">Morbi leo risus</button>
	<button type="button" class="list-group-item list-group-item-action">Porta ac consectetur ac</button>
	<button type="button" class="list-group-item list-group-item-action" disabled>Vestibulum at eros disabled</button>
</ul>
```

* With badges(帶標籤)  

<ul class="list-group w-50">
  <li class="list-group-item d-flex justify-content-between align-items-center">
  	Cras justo odio
  	<span class="badge badge-primary badge-pill">14</span>
	</li>
  <li class="list-group-item  d-flex justify-content-between align-items-center">
  Dapibus ac facilisis in
  	<span class="badge badge-primary badge-pill">2</span>
	</li>
  <li class="list-group-item  d-flex justify-content-between align-items-center">
  Morbi leo risus
  	<span class="badge badge-primary badge-pill">1</span>
	</li>
</ul>

```html
<ul class="list-group w-50">
  <li class="list-group-item d-flex justify-content-between align-items-center">
  	Cras justo odio
  	<span class="badge badge-primary badge-pill">14</span>
	</li>
  <li class="list-group-item  d-flex justify-content-between align-items-center">
  Dapibus ac facilisis in
  	<span class="badge badge-primary badge-pill">2</span>
	</li>
  <li class="list-group-item  d-flex justify-content-between align-items-center">
  Morbi leo risus
  	<span class="badge badge-primary badge-pill">1</span>
	</li>
</ul>
```

