## [Python Guide](./python_guide.md)

## 中古手機專賣店-MySQL
* **add project using MySQL**  
	* create project and app  
	```
	django-admin startproject sellphoneqsl  
	cd sellphoneqsl  
	python manage.py startapp secondphone  
	```

	* system setting
	sellphoneqsl/settings.py  
	```python
	# add app 
	INSTALLED_APPS = [
	    'django.contrib.admin',
	    'django.contrib.auth',
	    'django.contrib.contenttypes',
	    'django.contrib.sessions',
	    'django.contrib.messages',
	    'django.contrib.staticfiles',
	    'secondphone.apps.SecondphoneConfig',
	]
	# set language and time zone
	LANGUAGE_CODE = 'zh-Hant'
	TIME_ZONE = 'Asia/Taipei
	# set MySQl DB  
	DATABASES = {
	    'default': {
	        'ENGINE': 'django.db.backends.mysql',
	        'NAME': 'VwS4x0pD7o',
	        'USER': 'VwS4x0pD7o',
	        'PASSWORD': 'OnuPj2SsD9',
	        'HOST': 'remotemysql.com',
	        'PORT': ' 3306',
	    }
	}
	# set wait DB re-try 
	# remote may be more 5000~10000
	DATA_UPLOAD_MAX_NUMBER_FIELDS = 1000
	```

	* install mysqlclient  
	```
	conda install mysqlclient
	```

	* check set up  
	```
	python manage.py check
	```

	* app models  
	secondphone/models.py  
	```python
	from django.db import models
	class Maker(models.Model):
		name = models.CharField(max_length=10)
		country = models.CharField(max_length=10)
		def __str__(self):
			return self.name
	class PModel(models.Model):
		make = models.ForeignKey(Maker, on_delete=models.CASCADE) 
		name = models.CharField(max_length=20)
		url = models.URLField(default='https://ss7.vzw.com/is/image/VerizonWireless/iphone7-front-matblk?$png8alpha256$&hei=520')
		def __str__(self):
			return self.name
	class Product(models.Model):
		pmodel = models.ForeignKey(PModel, on_delete=models.CASCADE, verbose_name="型號")
		nickname = models.CharField(max_length=15, default='超級二手機', verbose_name="摘要")
		description = models.TextField(default='暫無說明')
		year = models.PositiveIntegerField(default=2016, verbose_name="出廠年份")
		price = models.PositiveIntegerField(default=0, verbose_name="價格")
		def __str__(self):
			return self.nickname
	class PPhoto(models.Model):
		product = models.ForeignKey(Product, on_delete=models.CASCADE) 
		description = models.CharField(max_length=20, default="產品照片")
		url = models.URLField(default='https://i5.walmartimages.com/asr/e82d7b52-8231-4ae8-8265-4e51fa26c5a1_2.09e8f3ddc9ef442cdeffb2f5485ada64.png?odnWidth=450&odnHeight=450&odnBg=ffffff')
		def __str__(self):
			return self.description
	```

	* register models  
	secondphone/admin.py
	```python
	from django.contrib import admin
	from .models import Maker
	from .models import PModel
	from .models import Product
	from .models import PPhoto
	class MakerAdmin(admin.ModelAdmin):
	  list_display = ( 'name', 'country')
	admin.site.register(Maker, MakerAdmin)
	admin.site.register(PModel)
	# admin.site.register(Product)
	class ProductAdmin(admin.ModelAdmin):
	  list_display = ( 'pmodel', 'nickname', 'price' , 'year')
	  search_fields = ('nickname',)
	  ordering = ('-price',)
	admin.site.register(Product, ProductAdmin)
	admin.site.register(PPhoto)
	```

	* migrate  
	```
	python manage.py makemigrations
	python manage.py migrate
	```

	* create super user 
	```
	python manage.py createsuperuser
	```

	* run server 
	```
	python manage.py runserver
	http://127.0.0.1:8000
	http://127.0.0.1:8000/admin/
	```

* add other part  
	* VS code set for Django
	```python
	{
	  "emmet.includeLanguages": {"django-html": "html"},
	  "python.linting.pylintArgs": [
	      "--load-plugins=pylint_django"
	  ],
	}
	```

	* system urls  
	sellphoneqsl/urls.py
	```python
	from django.contrib import admin
	from django.urls import path, include
	urlpatterns = [
	    path('', include('secondphone.urls')),
	    path('admin/', admin.site.urls),
	]
	```

	* app urls  
	secondphone/urls.py
	```python
	from django.urls import path, re_path
	from . import views
	urlpatterns = [
		path('', views.index, name='index'),
		re_path(r'^detail/(?P<id>\d+)/$', views.detail, name='detail'),
	]
	```

	* add app view  
	secondphone/views.py
	```python
	from django.shortcuts import render
	from django.http import HttpResponse
	from .models import Product
	from .models import PPhoto
	def  index(request):
		products = Product.objects.all()
		return render(request, 'second/index.html', locals())
	def  detail(request, id):
		try :
			product = Product.objects.get(id=id)
			image = PPhoto.objects.filter(product=product)
		except :
			pass
		return render(request, 'second/detail.html', locals())
	```

	* add template  
	template/second/base.html  
	```html
	<!DOCTYPE html>
	<html lang="en">
	{% load sass_tags %}
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<!-- bootstrap4 -->
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
		<link href="{% sass_src 'scss/style.scss' %}" rel="stylesheet" type="text/css" />
		<title>
			{% block title %} {% endblock  %}
		</title>
	</head>
	<body>
		{% include "second/header.html" %}
		{% block content %} {% endblock  %}
		<hr>
		{% include "second/footer.html" %}
		<!-- bootstrap4 -->
		<!-- Optional JavaScript -->
		<!-- jQuery first, then Popper.js, then Bootstrap JS -->
		<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
		<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
		<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
	</body>
	</html>
	```

	template/second/header.html  
	```html
	<nav class="navbar navbar-light bg-light d-flex justify-content-start">
	    <!-- brand -->
	    <a class="navbar-brand" href="/">中古機賣場</a>
	    <a class="nav-item nav-link active" href="/">Home</a>
	    <a class="nav-item nav-link" href="/admin/">後臺管理</a>
	</nav>
	```

	template/second/footer.html  
	```html
	{% load static %}
	<div class="d-flex justify-content-center">
		<img src="{% static 'images/flower.jpg' %}" alt="">
		<h3 class="inline mt-2">The finest second phone</h3>
	</div>
	```
	template/second/index.html  
	```html
	<!--    index.html -->
	{% extends "second/base.html" %}
	{% block  title %}中古機賣場{% endblock %} 
	{% block content %}

		<div class="row">
			<div class="col-6 m-auto">
				<table class="table table-striped">
				{% for p in products %}
					{% if forloop.first %}
					<thead>
						<tr class="table-secondary">
						<th scope="col">庫存手機</th>
						<th scope="col">廠牌/型號</th>
						<th scope="col">出廠年</th>
						<th scope="col">售價</th>
						</tr>
					</thead>
					<tbody>
					{% endif %}
					{% if  forloop.counter|divisibleby:2 %}
							<tr class="bg-success">
					{% else %}
							<tr class="bg-danger">
					{% endif %}
							<td><a href="detail/{{ p.id }}/">{{p.nickname}}</a></td>
							<td>{{p.pmodel.make.name}}/{{p.pmodel}}</td>
							<td>{{p.year}}</td>
							<td>{{p.price}}</td>
							</tr>		
					{% if forloop.last %}
					</tbody>
					</table>
					{% endif %}
					{% empty %}
					<h3>目前沒有庫存中古機可以賣,真抱歉</h3>
				{% endfor %}
			</div>
		</div>
	{% endblock  %}
	```

	template/second/detail.html  
	```html
	{% extends "second/base.html" %}
	{% block  title %}中古機賣場{% endblock %} 
	{% block content %}
		
		<div class="card text-center">
			<div class="card-body">
		{% if  product %}
				<h5 class="card-title mb-1">{{ product.nickname }}</h5>
				<p class="card-text mb-1">{{ product.description }}</p>
				<p class="card-text mb-1">西元{{ product.year }}年出廠</p>
				<p class="card-text mb-1">價格:NT${{ product.price }}元</p>
				{% for pic in image %}
					<img src="{{ pic.url }}" alt="" width=350><br>
				{% endfor %}
		{% else %}
				<h3>找不到指定手機</h3>
		{% endif %}
			</div>
		</div>
	{% endblock  %}
	```

	* static  
	secondphone/static/scss/style.css
	```css
	.navbar {
		.active {
			background-color: #b4b4b4 ;
		}
	}
	a {
		color: black;
	}
	```

	secondphone/static/images/flow.jpg

