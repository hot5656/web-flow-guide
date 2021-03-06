## [Bootstrap 4 Guide](./bootstrap4_guide.md)
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<meta http-equiv="X-UA-Compatible" content="ie=edge">
	<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
	<title>BS4 example</title>
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

## BS4 example

* 文字放於 block 中間  

<div class="d-flex bg-light mt-2 mb-3" style="height: 100px;">
	<div class="align-self-center mx-auto"><h3>～～心情休息站～～</h4></div>
</div>

```html
<div class="d-flex bg-light mt-2" style="height: 100px;">
	<div class="align-self-center mx-auto"><h3>～～心情休息站～～</h4></div>
</div>
```

* col 加間隔, 但不適合RWD(響應式網頁)  

<div class="row px-3 mt-2 pb-3">
	<div class="col card border border-primary px-0 ">
		<div class="card-header bg-primary text-white">Bill 開心</div>
		<div class="card-body">渭城朝雨邑輕塵，客舍青青柳色新。勸君更盡一杯酒，西出陽關無故人。</div>
		<div class="card-footer text-right">2019年11月6日 19:35</div>	
	</div>
	<div class="col card border border-primary px-0 mx-4">
		<div class="card-header bg-primary text-white">訪客 生氣</div>
		<div class="card-body">渭城朝雨邑輕塵，客舍青青柳色新。勸君更盡一杯酒，西出陽關無故人。</div>
		<div class="card-footer text-right">2019年11月6日 19:37</div>	
	</div>
	<div class="col card border border-primary px-0 ">
		<div class="card-header bg-primary text-white">阿良 開心</div>
		<div class="card-body">渭城朝雨邑輕塵，客舍青青柳色新。勸君更盡一杯酒，西出陽關無故人。</div>
		<div class="card-footer text-right">2019年11月6日 19:38</div>	
	</div>
</div>

```html
<div class="row px-3 mt-2">
	<div class="col card border border-primary px-0 ">
		<div class="card-header bg-primary text-white">Bill 開心</div>
		<div class="card-body">渭城朝雨邑輕塵，客舍青青柳色新。勸君更盡一杯酒，西出陽關無故人。</div>
		<div class="card-footer text-right">2019年11月6日 19:35</div>	
	</div>
	<div class="col card border border-primary px-0 mx-4">
		<div class="card-header bg-primary text-white">訪客 生氣</div>
		<div class="card-body">渭城朝雨邑輕塵，客舍青青柳色新。勸君更盡一杯酒，西出陽關無故人。</div>
		<div class="card-footer text-right">2019年11月6日 19:37</div>	
	</div>
	<div class="col card border border-primary px-0 ">
		<div class="card-header bg-primary text-white">阿良 開心</div>
		<div class="card-body">渭城朝雨邑輕塵，客舍青青柳色新。勸君更盡一杯酒，西出陽關無故人。</div>
		<div class="card-footer text-right">2019年11月6日 19:38</div>	
	</div>
</div>
```

* card 移至下一城層即ok,適合RWD(響應式網頁)  

<div class="row my-3">
	<div class="col-4">
		<div class="card">
			<div class="card-header bg-primary text-white">Bill 開心</div>
			<div class="card-body">渭城朝雨邑輕塵，客舍青青柳色新。勸君更盡一杯酒，西出陽關無故人。</div>
			<div class="card-footer text-right">2019年11月6日 19:35</div>
		</div>
	</div>
	<div class="col-4">
		<div class="card">
			<div class="card-header bg-primary text-white">訪客 生氣</div>
			<div class="card-body">渭城朝雨邑輕塵，客舍青青柳色新。勸君更盡一杯酒，西出陽關無故人。</div>
			<div class="card-footer text-right">2019年11月6日 19:37</div>
		</div>
	</div>
	<div class="col-4">
		<div class="card">
			<div class="card-header bg-primary text-white">阿良 開心</div>
			<div class="card-body">渭城朝雨邑輕塵，客舍青青柳色新。勸君更盡一杯酒，西出陽關無故人。</div>
			<div class="card-footer text-right">2019年11月6日 19:38</div>
		</div>
	</div>
</div>

```html
<div class="row my-3">
	<div class="col-4">
		<div class="card">
			<div class="card-header bg-primary text-white">Bill 開心</div>
			<div class="card-body">渭城朝雨邑輕塵，客舍青青柳色新。勸君更盡一杯酒，西出陽關無故人。</div>
			<div class="card-footer text-right">2019年11月6日 19:35</div>
		</div>
	</div>
	<div class="col-4">
		<div class="card">
			<div class="card-header bg-primary text-white">訪客 生氣</div>
			<div class="card-body">渭城朝雨邑輕塵，客舍青青柳色新。勸君更盡一杯酒，西出陽關無故人。</div>
			<div class="card-footer text-right">2019年11月6日 19:37</div>
		</div>
	</div>
	<div class="col-4">
		<div class="card">
			<div class="card-header bg-primary text-white">阿良 開心</div>
			<div class="card-body">渭城朝雨邑輕塵，客舍青青柳色新。勸君更盡一杯酒，西出陽關無故人。</div>
			<div class="card-footer text-right">2019年11月6日 19:38</div>
		</div>
	</div>
</div>
```


* alert  

<div class="alert alert-warning">warning message...</div>

```html
<div class="alert alert-warning">warning message...</div>
```

* font awesome icon  

<!-- size -->
<i class="fa fa-camera-retro fa"></i> fa
<i class="fa fa-camera-retro fa-lg"></i> fa-lg(33%+)
<i class="fa fa-camera-retro fa-2x"></i> fa-2x
<i class="fa fa-camera-retro fa-3x"></i> fa-3x
<i class="fa fa-camera-retro fa-4x"></i> fa-4x
<i class="fa fa-camera-retro fa-5x"></i> fa-5x
<!-- aria-hidden 對 bootstrap 會有影響(有較好) -->
<i class="fa fa-trash" aria-hidden="true">
<!-- 合併icon fa-square-o*2 fa-twitter*1-->
<span class="fa-stack fa-lg">
	<i class="fa fa-square-o fa-stack-2x"></i>
	<i class="fa fa-twitter fa-stack-1x"></i>
</span>
<!-- 合併icon text-color control color -->
<span class="fa-stack fa-lg">
	<i class="fa fa-camera fa-stack-1x"></i>
	<i class="fa fa-ban fa-stack-2x text-danger"></i>
</span>

```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

<!-- size -->
<i class="fa fa-camera-retro fa"></i> fa
<i class="fa fa-camera-retro fa-lg"></i> fa-lg(33%+)
<i class="fa fa-camera-retro fa-2x"></i> fa-2x
<i class="fa fa-camera-retro fa-3x"></i> fa-3x
<i class="fa fa-camera-retro fa-4x"></i> fa-4x
<i class="fa fa-camera-retro fa-5x"></i> fa-5x
<!-- aria-hidden 對 bootstrap 會有影響(有較好) -->
<i class="fa fa-trash" aria-hidden="true">
<!-- 合併icon fa-square-o*2 fa-twitter*1-->
<span class="fa-stack fa-lg">
	<i class="fa fa-square-o fa-stack-2x"></i>
	i class="fa fa-twitter fa-stack-1x"></i>
</span>
<!-- 合併icon text-color control color -->
<span class="fa-stack fa-lg">
	<i class="fa fa-camera fa-stack-1x"></i>
	<i class="fa fa-ban fa-stack-2x text-danger"></i>
</span>
```

* icon onclick control  
但選擇後會留有外框  

<button type="button" class="btn" onclick=del_post()><i class="fa fa-trash" aria-hidden="true"></i></button>

```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
<button type="button" class="btn" onclick=del_post({{ p.id }})><i class="fa fa-trash" aria-hidden="true"></i></button>
```

* 文字放於一行兩邊  

<div class="d-flex justify-content-between">
	<div>item1</div>
	<div>item2</div>
</div>

```html
<div class="d-flex justify-content-between">
	<div>item1</div>
	<div>item2</div>
</div>
```