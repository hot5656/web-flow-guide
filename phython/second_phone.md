## [Python Guide](./python_guide.md)

## 中古手機專賣店
* **simple 1st**
	* create project and app  
	django-admin startproject sellphone  
	cd sellphone  
	python manage.py startapp secondphone  

	* system setting  
	sellphone/settings.py  
	```python
	INSTALLED_APPS = [
	    'django.contrib.admin',
	    'django.contrib.auth',
	    'django.contrib.contenttypes',
	    'django.contrib.sessions',
	    'django.contrib.messages',
	    'django.contrib.staticfiles',
	    'secondphone.apps.SecondphoneConfig',
	]
	LANGUAGE_CODE = 'zh-Hant'
	TIME_ZONE = 'Asia/Taipei'
	```

	* system urls  
	sellphone/urls.py  
	```python
	from django.contrib import admin
	from django.urls import path, include
	urlpatterns = [
	    path('', include('secondphone.urls')),
	    path('admin/', admin.site.urls),
	]
	```

	* app urls  
	sellphone/urls.py  
	```python
	from django.urls import path, re_path
	from . import views
	urlpatterns = [
	    path('', views.index, name='index'),
			path('about/', views.about, name='about'),
			path('list/', views.list, name='list'),
			re_path(r'^list/(?P<pk>\d+)/$', views.detail, name='detail'),
	]
	```

	* app models  
	sellphone/models.py  
	```python
	from django.db import models
	class Product(models.Model):
		SIZES = (
			('S', 'Small'),
			('M', 'Medium'),
			('L', 'Large'),
		)
		sku = models.CharField(max_length=5)
		name = models.CharField(max_length=20)
		price = models.PositiveIntegerField()
		size = models.CharField(max_length=1, choices=SIZES)
	```

	* register models  
	sellphone/admin.py  
	```python
	from django.contrib import admin
	from .models import Product
	admin.site.register(Product)
	```

	* add temple view  
	sellphone/views.py  
	```python
	from django.shortcuts import render
	from django.http import HttpResponse
	def  index(request):
		return HttpResponse("index...")
	def  about(request):
		return HttpResponse("about...")
	def  list(request):
		return HttpResponse("list...")
	def  detail(request, pk):
		return HttpResponse("detail...%s" % pk)
	```

	* migrate  
	python manage.py makemigrations  
	python manage.py migrate  

	* create supersure then run server  
	python manage.py createsuperuser  
	python manage.py runserver  
	http://127.0.0.1:8000/  
	http://127.0.0.1:8000/admin/  
	http://127.0.0.1:8000/about/  
	http://127.0.0.1:8000/list/  
	http://127.0.0.1:8000/list/10/  
	http://127.0.0.1:8000/list/a/ - not accept  

* **complete code**  
	* basic vs code set for Django  
	```json
	{
		"emmet.includeLanguages": {"django-html": "html"},
		"python.linting.pylintArgs": [
			"--load-plugins=pylint_django"
		],
	}
	```

	* common template  
	sellphone/templates/base.html  
	```html
	<!DOCTYPE html>
	<html >
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
		<title>
			{% block title %} {% endblock  %}
		</title>
	</head>
	<body>
		{% include "header.html" %}
		<hr>
		{% block content %} {% endblock  %}
		<hr>
		{% include "footer.html" %}
	  <!-- Optional JavaScript -->
	  <!-- jQuery first, then Popper.js, then Bootstrap JS -->
	  <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
	  <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
	  <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
	</body>
	</html>
	```

	sellphone/templates/header.html  
	```html
	<h1>中古機販賣專門店</h1>
	```

	sellphone/templates/footer.html  
	```html
	<p>我們的存在是為了你的需求.....</p>
	```

	sellphone/templates/index.html  
	```html
	<!--	index.html -->
	{% extends "base.html" %}
	{% block  title %}Welcome to sellphone{% endblock %} 
	{% block content %}
		<ul>
			<li>
				<a href="/list">中古機列表</a>
			</li>
			<li>
				<a href="/about">關於我</a>
			</li>
		</ul>
	{% endblock  %}
	```

	sellphone/templates/about.html  
	```html
	<!--	about.html -->
	{% extends "base.html" %}
	{% block  title %}About me{% endblock %} 
	{% block content %}
		<h2>Robaet Kao</h2>
		<p>I am Robert Kao. Nice to meet you.</p>
		<a href="/">回主頁</a>
	{% endblock  %}
	```

	sellphone/templates/list.html  
	```html
	<!--	list.html -->
	{% extends "base.html" %}
	{% block  title %}中古手機列表{% endblock %} 
	{% block content %}
		<h2>本店中古手機列表</h2>
		<table border=1 width=400 bgcolor="ccffcc">
			<thead>
				<tr>
					<td>品名</td>
					<td>售價</td>
					<td>庫存量</td>
				</tr>
			</thead>
			<tbody>
				{% for p in products %}
					<tr>
						<td>
						<a href="/list/{{p.pk}}">{{p.name}}</a>
						</td>
						<td>{{p.price}}</td>
						<td>{{p.qty}}</td>
					</tr>
				{% endfor %}
			</tbody>
		</table>
		<a href="/">回主頁</a>
	{% endblock  %}
	```

	sellphone/templates/detail.html  
	```html
	<!--	detail.html -->
	{% extends "base.html" %}
	{% block  title %}{{product.name}}{% endblock %} 
	{% block content %}
		<h2>{{product.name}}</h2>
		<table border=1 width=400 bgcolor="ccffcc">
			<tbody>
					<tr>
						<td>品項編號</td>
						<td>{{product.sku}}</td>
					</tr>
					<tr>
						<td>品項名稱</td>
						<td>{{product.name}}</td>
					</tr>
					<tr>
						<td>二手售價</td>
						<td>{{product.price}}</td>
					</tr>
					<tr>
						<td>庫存數量</td>
						<td>{{product.qty}}</td>
					</tr>
			</tbody>
		</table>
		<a href="/">回主頁</a>
	{% endblock  %}
	```

	* change app models - add qty  
	sellphone/models.py  
	```python
	from django.db import models
	class Product(models.Model):
		# 品項編號
		sku = models.CharField(max_length=5)
		name = models.CharField(max_length=20)
		price = models.PositiveIntegerField()
		qty = models.PositiveIntegerField(default=0)
	```

	* admin for models show more field  
	sellphone/admin.py  
	```python
	from django.contrib import admin
	from .models import Product
	#admin.site.register(Product)
	# change Product admin list
	class ProductAdmin(admin.ModelAdmin):
		list_display = ( 'sku', 'name', 'price', 'qty')
	admin.site.register(Product, ProductAdmin)
	```

	* update view  
	sellphone/views.py  
	```python
	from django.shortcuts import render
	from django.http import HttpResponse, Http404
	from .models import Product
	def  index(request):
		return render(request, "index.html")
	def  about(request):
		return render(request, "about.html")
	def  list(request):
		products = Product.objects.all()
		return render(request, 'list.html', { 'products' : products, })
	def  detail(request, pk):
		# add not found
		try :
			product = Product.objects.get(pk=pk)
		except Product.DoesNotExist:
			raise Http404('找不到指定項目')
		return render(request, 'detail.html', { 'product' : product, })
	```