## [Bootstrap 4 Guide](./bootstrap4_guide.md)
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<meta http-equiv="X-UA-Compatible" content="ie=edge">
	<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
	<title>BS4 basic</title>
</head>
<body>

<!-- Optional JavaScript -->
<!-- jQuery first, then Popper.js, then Bootstrap JS -->
<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
</body>
</html>

## BS4 basic
* [Container](#Container)
* [Grid](#Grid)

<a id="Container"></a>
## Container [[Home]](#) 
```html
container : 1140px
container-fluid : 依 screen 變化
```

<a id="Grid"></a>
## Grid [[Home]](#) 
```
.row
.col-
```

* grid option  

xx      |Extra small|Small |Medium|Large |Extra large
--------|-----------|------|------|------|-----------
			|<576px   |≥576px|≥768px|≥992px|≥1200px
Max container width|None (auto)|540px|  720px|960px|1140px
Class prefix|.col-|.col-sm-|.col-md-|.col-lg-|.col-xl-

Gutter width : 30px (15px on each side of a column)
columns : 12

* columns layout  
	* Equal-width  
	<div class="container">
		<div class="row bg-light mb-2">
			<div class="col border ">
				1 of 2
			</div>
			<div class="col border">
				2 of 2
			</div>
		</div>
		<div class="row bg-light mb-2">
			<div class="col border">
				1 of 3
			</div>
			<div class="col border">
				2 of 3
			</div>
			<div class="col border">
				3 of 3
			</div>
		</div>
	</div>

	```html
	<div class="container">
		<div class="row">
			<div class="col">
				1 of 2
			</div>
			<div class="col">
				2 of 2
			</div>
		</div>
		<div class="row">
			<div class="col">
				1 of 3
			</div>
			<div class="col">
				2 of 3
			</div>
			<div class="col">
				3 of 3
			</div>
		</div>
	</div>
	```

	* Setting one column width  
	<div class="row bg-light mb-2">
		<div class="col border">
			1 of 3
		</div>
		<div class="col-6 border">
			2 of 3 (wider)
		</div>
		<div class="col border">
			3 of 3
		</div>
	</div>

	```html
	<div class="row">
		<div class="col">
			1 of 3
		</div>
		<div class="col-6">
			2 of 3 (wider)
		</div>
		<div class="col">
			3 of 3
		</div>
	</div>
	```

	* Variable width content  
	col-auto 表示依內容長度調整  
	<div class="row bg-light mb-2">
		<div class="col border">
			1 of 3
		</div>
		<div class="col-auto border">
			Variable width content
		</div>
		<div class="col-3 border">
			3 of 3
		</div>
	</div>

	```html
	<div class="row">
		<div class="col">
			1 of 3
		</div>
		<div class="col-auto">
			Variable width content
		</div>
		<div class="col-3">
			3 of 3
		</div>
	</div>
	```

	* Responsive classes(響應式 Classes)  
	依不同點classes 調整  
  <div class="row bg-light mb-2">
    <div class="col-12 col-md-8 border">.col-12 .col-md-8</div>
    <div class="col-6 col-md-4 border">.col-6 .col-md-4</div>
  </div>

	```html
  <div class="row">
    <div class="col-12 col-md-8">.col-12 .col-md-8</div>
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
  </div>
	```

	* Gutters  
	Gutters 指的是 col 的 padding, 可用 px py 等調整  
  <div class="row bg-light mb-2">
    <div class="col-12 col-md-8 py-3 px-5 border">.col-12 .col-md-8</div>
    <div class="col-6 col-md-4 py-3 px-5 border">.col-6 .col-md-4</div>
  </div>

  ```python
  <div class="row">
    <div class="col-12 col-md-8 py-3 px-5">.col-12 .col-md-8</div>
    <div class="col-6 col-md-4 py-3 px-5">.col-6 .col-md-4</div>
  </div>
  ```

	* No Gutters
  <div class="row no-gutters bg-light b-2">
    <div class="col-12 col-md-8 border">.col-12 .col-md-8</div>
    <div class="col-6 col-md-4 border">.col-6 .col-md-4</div>
  </div>

  ```html
  <div class="row no-gutters">
    <div class="col-12 col-md-8">.col-12 .col-md-8</div>
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
  </div>
  ```

	* Column breaks  
	中斷你的欄到新的一行，可增加一個元素 w-100   
  <div class="row bg-light mb-2">
    <div class="col border">col</div>
    <div class="col border">col</div>
    <div class="w-100"></div>
    <div class="col border">col</div>
    <div class="col border">col</div>
  </div>

	```html
  <div class="row">
    <div class="col">col</div>
    <div class="col">col</div>
    <div class="w-100"></div>
    <div class="col">col</div>
    <div class="col">col</div>
  </div>
	```

	* Order classes(排序)  
	order-1 ~ order-12, order-first order-last  
  <div class="row bg-light mb-2">
    <div class="col border">
      First, but unordered
    </div>
    <div class="col order-12 border">
      Second, but last
    </div>
    <div class="col order-1 border">
      Third, but first
    </div>
  </div>

	```html
  <div class="row">
    <div class="col">
      First, but unordered
    </div>
    <div class="col order-12">
      Second, but last
    </div>
    <div class="col order-1">
      Third, but first
    </div>
  </div>
	```

	* Offset classes(欄的推移) 
  <div class="row bg-light mb-2">
    <div class="col-md-4 border">.col-md-4</div>
    <div class="col-md-4 offset-md-4 border">.col-md-4 .offset-md-4</div>
  </div>
  <div class="row bg-light mb-2">
    <div class="col-md-3 offset-md-3 border">.col-md-3 .offset-md-3</div>
    <div class="col-md-3 offset-md-3 border">.col-md-3 .offset-md-3</div>
  </div>
  <div class="row bg-light mb-2">
    <div class="col-md-6 offset-md-3 border">.col-md-6 .offset-md-3</div>
  </div>

	```html
  <div class="row">
    <div class="col-md-4">.col-md-4</div>
    <div class="col-md-4 offset-md-4">.col-md-4 .offset-md-4</div>
  </div>
  <div class="row">
    <div class="col-md-3 offset-md-3">.col-md-3 .offset-md-3</div>
    <div class="col-md-3 offset-md-3">.col-md-3 .offset-md-3</div>
  </div>
  <div class="row">
    <div class="col-md-6 offset-md-3">.col-md-6 .offset-md-3</div>
  </div>
	```

