# phython django

*   [Root](../README.md)

<style>
.Maroon { 
color:Maroon; 
}
.Red { 
color:Red; 
}
.Orange { 
color:Orange; 
}
.Yellow { 
color:Yellow; 
}
.Olive { 
color:Olive; 
}
.Green { 
color:Green; 
}

.Purple { 
color:Purple; 
}

.Fuchsia { 
color:Fuchsia; 
}
.Lime { 
color:Lime; 
}
.Teal { 
color:Teal; 
}
.Aqua { 
color:Aqua; 
}
.Blue { 

color:Blue; 
}
.Navy { 
color:Navy; 
}

.Fb{
font-weight:bold;
}
</style>


## 1. mblog  
* **create project**  
django-admin startproject mblog  
cd mblog  
python manage.py runserver  
http://127.0.0.1:8000/  

* **add app**  
	* create app  
	python manage.py startapp mainsite  

	* setting  
	mblog/settings.py  
	```python
	INSTALLED_APPS = [
	    'django.contrib.admin',
	    'django.contrib.auth',
	    'django.contrib.contenttypes',
	    'django.contrib.sessions',
	    'django.contrib.messages',
	    'django.contrib.staticfiles',
	    #  'mainsite' or 'mainsite.apps.MainsiteConfig'
	    'mainsite.apps.MainsiteConfig',
	]
	LANGUAGE_CODE = 'zh-Hant'
	TIME_ZONE = 'Asia/Taipei'
	```

	* set models  
	mainsite/models.py  
	```python
	from django.db import models
	from django.utils import timezone 
	class Post(models.Model):
		title = models.CharField(max_length=200)
		slug = models.CharField(max_length=200)
		body = models.TextField()
		pub_date = models.DateField(default=timezone.now)
		class Meta: 
			ordering = ('-pub_date',)
		def __str__(self): 
			return self.title
	```
	> slug : 文章網址  

	* create migrate  
	python manage.py makemigrations mainsite  
	> 建立DB and Django 間的中介檔案

	* migrate  
	python manage.py migrate
	> 同步更新DB內容  

	* create super user  
	python manage.py createsuperuser  

	* register Post  
	mainsite/admin.py
	```python
	from django.contrib import admin
	from .models import Post
	admin.site.register(Post)
	```

	* access admin  
	http://127.0.0.1:8000/admin/  

* **show DB list more field**  
```python
from .models import Post
class PostAdmin(admin.ModelAdmin):
	list_display = ( 'title', 'slug', 'pub_date')
admin.site.register(Post, PostAdmin)
```
http://127.0.0.1:8000/admin/  

* **show app data**  
	* app views  
	mainsite/view.py  
	```python
	from django.shortcuts import render
	from django.http import HttpResponse
	from .models import Post
	def homepage(request):
		posts = Post.objects.all()
		post_lists = list()
		for count, post in enumerate(posts):
			post_lists.append("No.{}:".format(str(count))+ str(post)+"<br>")
		return HttpResponse(post_lists)	
	```

	* app urls
	mblog/urls.py  
	```python
	from mainsite.views import homepage
	urlpatterns = [
	    path('', homepage),
	    path('admin/', admin.site.urls),
	]
	```

	* access app homepage  
	http://127.0.0.1:8000/

	* add show field body  
	```python
	def homepage(request):
		posts = Post.objects.all()
		post_lists = list()
		for count, post in enumerate(posts):
			post_lists.append("No.{}:".format(str(count))+ str(post)+"<hr>")
			post_lists.append("<small>"+str(post.body)+"</small><br><br>")
		return HttpResponse(post_lists)	
	```

* **add template**  
	* default TEMPLATES APP_DIRS set true  already  
	mblog/settings.py  
	```python
	TEMPLATES = [
	    {
	        'BACKEND': 'django.template.backends.django.DjangoTemplates',
	        'DIRS': [],
	        # set APP_DIRS already 
	        'APP_DIRS': True,
	        'OPTIONS': {
	            'context_processors': [
	                'django.template.context_processors.debug',
	                'django.template.context_processors.request',
	                'django.contrib.auth.context_processors.auth',
	                'django.contrib.messages.context_processors.messages',
	            ],
	        },
	    },
	]
	```

	* change view for template  
	mainsite/view.py  
	```python
	from django.shortcuts import render
	from datetime import datetime
	from .models import Post
	def homepage(request):
		posts = Post.objects.all()
		now = datetime.now()
		content = {
			'posts' : posts,
			'now' : now,
		}
		return render(request, 'index.html', content)
	```
	> 'posts', 'now' are the parameter to template  

	*  add template directory  
	mainsite/templates/index.html  
	```html
	<!DOCTYPE html>
	<html>
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>歡迎光臨</title>
	</head>
	<body>
		<h1>部落格</h1>
		<hr>
		{{posts}}
		<hr>
		<h3>現在時刻:{{now}}</h3>
	</body>
	</html>
	```
	> {{posts}}, {{now}} are the parameter from view  

	* access app homepage  
	http://127.0.0.1:8000/

	* show some field  
	mainsite/templates/index.html  
	```html
	<hr>
	{% for  post in  posts %}
		<!-- 微軟正黑體 -->
		<p style="font-family:DFKai-sb;font-size:16pt;font-weight:bold;">{{post.title}}</p>
		<p style="font-family:DFKai-sb;font-size:10pt;letter-spacing:1pt">{{post.body}}</p>
	{% endfor %}
	<hr>
	```

	* show title and add link  
	```html
	<hr>
	{% for  post in  posts %}
		<!-- 微軟正黑體 -->
		<p style="font-family:DFKai-sb;font-size:16pt;font-weight:bold;">
			<a href="post/{{post.pk}}">{{post.title}}</a>
		</p>
	{% endfor %}
	<hr>
	```
* **show detail one page**  
	* change system urls - point app urls  
	mblog/urls.py  
	```python
	from django.contrib import admin
	from django.urls import path, include 
	urlpatterns = [
	    path('', include('mainsite.urls')),
	    path('admin/', admin.site.urls),
	]
	```
	> path('', include('mainsite.urls')) : map urls to mainsite.urls  

	* add app urls  
	mainsite/urls.py  
	```python
	from django.urls import path, re_path
	from . import views
	urlpatterns = [
	    path('', views.homepage, name='homepage'),
		re_path(r'^post/(?P<pk>\w+)/$', views.showpost, name='showpost'),
	]
	```
	> (r'^post/(?P<pk>\w+)/$' : link post/pk/

	* add views's showpost  
	mainsite/views.py  
	```python
	from django.shortcuts import redirect
	from .models import Post
	def showpost(request, pk):
		try:
			post = Post.objects.get(pk=pk)
			if post != None:
				return render(request, 'post.html', {'post' : post,})
		except:
			return redirect('/')
	```
	> redirect('/') : redirect to main page  

	* add template post.html  
	mainsite/templates/post.html  
	```html
	<!DOCTYPE html>
	<html>
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>Post show</title>
	</head>
	<body>
		<h1>{{post.title}}</h1>
		<hr>
			<p style="font-family:DFKai-sb;font-size:12pt;letter-spacing:2pt">{{post.body}}</p>
		<hr>
		<h3><a href="/">回首頁</a></h3>
	</body>
	</html>
	```
	> <a href="/">回首頁</a> : to main page  

* **common template**  
	* base.html  
	```html
	<!-- base.html -->
	<!DOCTYPE html>
	<html>
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>
			{% block  title %} {% endblock  %}
		</title>
	</head>
	<body>
		{% include "header.html" %}
		{% block  headmessage %} {% endblock  %}
		<hr>
		{% block content %} {% endblock  %}
		<hr>
		{% include "footer.html" %}
	</body>
	</html>
	```

	* header.html  
	```html
	<!-- header.html -->
	<h1>歡迎光臨 文學天地</h1>
	```

	* footer.html  
	```html
	<!-- footer.html -->
	{% block footer %}
		{% if now %}
			<p>現在時刻:{{now}}</p>
		{% else %}
			<p>摘自網路...</p>
		{% endif %}
	{% endblock  %}
	```

	* index.html  
	```html
	<!-- index.html -->
	{% extends "base.html" %}
	{% block  title %} 歡迎光臨 {% endblock  %}
	{% block  headmessage %}
		<h3>文章列表</h3>
	{% endblock  %}
	{% block  content %}
		{% for  post in  posts %}
			<!-- 微軟正黑體 -->
			<p style="font-family:DFKai-sb;font-size:16pt;font-weight:bold;">
				<a href="post/{{post.pk}}">{{post.title}}</a>
			</p>
		{% endfor %}
	{% endblock  %}
	```

	* post.html
	```html
	<!-- post.html -->
	{% extends "base.html" %}
	{% block  title %} 文學天地 {% endblock  %}
	{% block  headmessage %}
		<h3>{{post.title}}</h3>
		<a href="/">回首頁</a>
		<h3> 文章列表</h3>
	{% endblock  %}
	{% block  content %}
		<p style="font-family:DFKai-sb;font-size:12pt;letter-spacing:2pt">{{post.body}}</p>
	{% endblock  %}
		```
* **add bootstrap**  
	* add css and JS for bootstrap  
	mainsite/templates/base.html  
	```html
	<!-- base.html -->
	<!DOCTYPE html>
	<html>
	<head>
		....
		<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
		<title>
			{% block  title %} {% endblock  %}
		</title>
	</head>
	<body>
		....
	    <!-- Optional JavaScript -->
	    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
		<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
		<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
		<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
	</body>
	</html>
	```

	* add menu + base show   
	mainsite/templates/base.html  
	```html
	<!-- or <div class="container"> -->
	<div class="container-fluid">
		{% include "header.html" %}
		<!-- mt-4: add margin top-->
		<div class="row mt-4">
			<div class="col-sm-4 col-md-4">
				<!-- card -->
				<div class="card">
					<div class="card-header">
						<h3>MENU</h3>
					</div>
					<div class="card-body">
						<!-- list -->
						<div class="list-group">
							<a href="/" class="list-group-item">Home</a>
							<a href="https://tw.news.yahoo.com/" class="list-group-item">即時新聞</a>
							<a href="https://tw.news.yahoo.com/most-popular" class="list-group-item">熱門新聞</a>
							<a href="/"><img src="http://guestscounter.com/count.php?c_style=16&id=1570587774" border=0 alt="free counter"></a><br>
						</div>
					</div>
				</div>
			</div>
			<div class="col-sm-8 col-md-8">
				<!-- card -->
				<div class="card">
					<div class="card-header">
						{% block  headmessage %} {% endblock  %}
					</div>
					<div class="card-body">
						{% block content %} {% endblock  %}
					</div>
					<div class="card-footer">
						{% include "footer.html" %}
					</div>
				</div>
			</div>
		</div>
	</div>
	```

	* header  
	mainsite/templates/header.html  
	```html
	<!-- card-header for title -->
	<div class="card card-header">
		<h1>歡迎光臨 文學天地</h1>
	</div>
	```

	* free counter example  
	```html
	<a href="/"><img src="http://guestscounter.com/count.php?c_style=16&id=1570587774" border=0 alt="free counter"></a><br>
	```

	* change title to image - from static position  
	add image to mainsite\static\images\flower.jpg  
	mainsite/templates/header.html  
	```html
	<!-- header.html -->
	<!-- need load static 1st-->
	{% load static %}
	<!-- card-header for title -->
	<div class="card card-header">
		<!-- <h1>歡迎光臨 文學天地</h1> -->
		<img src="{% static 'images/flower.jpg' %}" alt="" height="64" width="64">
	</div>
	```

	* change pub_date  
	```
	pub_date = models.DateField(default=timezone.now)
	to 
	pub_date = models.DateTimeField(default=timezone.now)
	```

	* show body HTML  
	```html
	{{post.body | safe }}
	```

	* markdown support  
	conda install markdown - install makrdown  
	views.py - import markdown and process  
	```python
	import markdown # 導入markdown
	def showpost(request, pk):
		try:
			post = Post.objects.get(pk=pk)
			# post.dody support markdown
			post.body = markdown.markdown(post.body,
				extensions=[
				# 包含縮寫、表格等常用擴展
				'markdown.extensions.extra',
				# 語法高亮擴展
				'markdown.extensions.codehilite',
				# 允許我們自動生成目錄
				'markdown.extensions.toc',
				])
			if post != None:
				return render(request, 'post.html', {'post' : post,})
		except:
			return redirect('/')
	```
	html simulate for markdown - so need add safe option  
	```html
	{{post.body | safe }}
	```

## 2. 中古手機專賣店  
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

## 3. TV and car  
django-admin startproject tvacar
cd tvacar

python manage.py startapp tvs
python manage.py startapp car

	* system setting  
	tvacar/settings.py  
	```python
	INSTALLED_APPS = [
	    'django.contrib.admin',
	    'django.contrib.auth',
	    'django.contrib.contenttypes',
	    'django.contrib.sessions',
	    'django.contrib.messages',
	    'django.contrib.staticfiles',
	    #'tvs',
	    'tvs.apps.TvsConfig',
	    'car.apps.CarConfig',
	]
	LANGUAGE_CODE = 'zh-Hant'
	TIME_ZONE = 'Asia/Taipei'
	```

	* system urls  
	tvacar/urls.py  
	```python
	from django.contrib import admin
	from django.urls import path, include
	urlpatterns = [
	    path('admin/', admin.site.urls),
	    path('car/', include('car.urls')),
	    path('', include('tvs.urls')),
	]
	```

	* app urls  
	tvs/urls.py  
	```python
	from django.urls import path, re_path
	from . import views
	urlpatterns = [
		path('', views.home ),
		path('tvs/index', views.index ),
	]
	```

	* app urls  
	car/urls.py  
	```python
	from django.urls import path, re_path
	from . import views
	urlpatterns = [
		path('index', views.index ),
	]
	```

	tvs/views.py  
	```python
	from django.shortcuts import render
	from django.http import HttpResponse
	def home(request):
		return HttpResponse("home...")
	def index(request):
		return HttpResponse("tvs index...")
	```

	car/views.py  
	```python
	from django.shortcuts import render
	from django.http import HttpResponse
	def index(request):
		return HttpResponse("car index...")
	```

	python manage.py runserver
	http://127.0.0.1:8000/
	http://127.0.0.1:8000/tvs/index
	http://127.0.0.1:8000/car/index
	http://127.0.0.1:8000/admin

* **..**
	* TV embedded link  
	```html
	台視 <iframe width="560" height="315" src="https://www.youtube.com/embed/NbjI0cARzjQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	民視 <iframe width="560" height="315" src="https://www.youtube.com/embed/XxJKnDLYZz4" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	中天 <iframe width="560" height="315" src="https://www.youtube.com/embed/wUPPkSANpyo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	東森 <iframe width="560" height="315" src="https://www.youtube.com/embed/RaIJ767Bj_M" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	Sky <iframe width="560" height="315" src="https://www.youtube.com/embed/zg_YUu2JzEA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	ABC <iframe width="560" height="315" src="https://www.youtube.com/embed/nu3iXDR7iXo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	DW <iframe width="560" height="315" src="https://www.youtube.com/embed/NvqKZHpKs-g" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	```


## .Django reference  
* **[Built-in template tags and filters](https://docs.djangoproject.com/en/2.2/ref/templates/builtins/)**  
```
{{post.body | truncatechars:40 }} : only show previous 40 words  
發布時間 : {{post.pub_date | date:"Y M D h:m:s"}} : show time format 
wordcount : words counter  
striptags : remove all HTML tags  
```

* **[Model field reference](https://docs.djangoproject.com/en/2.2/ref/models/fields/#django.db.models.DateTimeField)**
```python
BigIntegerField : 64bits int
BooleanField : Boolen(True/False)
CharField : max_length(較短的字串)
DateField : datetime.date (auto_now-update update, auto_now_add-add update)
DateTimeField : datetime.datetime
DecimalField : max_digits-最大位數, decimal_places-小數位數
EmailField : max_length(for email address)
FloatField : 
IntegerField : 整數
PostivelIntegerField : 正整數
SulgField : max_length(網址的一部份)
TextField : 長文字格式
URLField : max_length(存完整網址)
# 屬性
null : accept null(default False)  
black : accept 空白(default False)  
choices : 選項方式  
> SIZE = (
> 		('S', 'Small'),
> 		('M', 'Medium'),
> 		('L', 'Latge'),
> 	)
> size = models.CharField(max_length=1, choices=SIZE)
default : default value  
help_text : field help message  
primary_key : 主key(default False)  
unique : 設定為一值(default False)  
```

* **Django ORM(object-relational mapping)**  
[Full Stack Python-ORM](https://www.fullstackpython.com/django-orm.html)  
[Django ORM Cookbook](https://books.agiliq.com/projects/django-orm-cookbook/en/latest/)  
```python
xxx.object.all()
xxx.objects.create(..)
...
# 常用
Filter() : 傳回符合條件
exclude() : 傳回不符合條件  
order_by() : 對某欄位排序
all() : all 
get() : get on condition(if no or over 1 --> exception)
first()/last() :  1st/last item
aggregate() : 計算函數的聚合函數
exists() : 檢查是否存在某條件之紀錄,通常附在filter()後面
update() : 更新欄位內容
delete() : 刪除指定紀錄
iexact : 不區分大小寫條件
contains/icontains : 設定含有某一字串即符合 
in : 提供一串列,只要符合串列內任一值均可
gt/gte/lt/lte : 大於/大於等於/小於/小於等於
> Product.object.filter(qty_lt=2) - 條件小於2  
> Product.object.all().order_by('price') - 以 price 排序
> Product.object.all().order_by('price') - 以 price 排序由大到小
> Product.object.filter(price_lte=800).aggregate(Sum('qty')) - 價格低於800共有多少
> Product.object.filter(name_icontains='sony') - 找出sony手機
> Product.object.filter(qty_in=[1,2]) - 找出數量為 1 or 2 手機
> Product.object.filter(name_contains='SONY').exists() - 是否有sony手機
> 若找不到資料 filter會傳回一個空字串,get 會產生一個 DoesNotExist 例外,超過一個也會產生例外
```

* **[Regular expression operations](https://docs.python.org/3/library/re.html#re.MULTILINE)**  

```python
re_path(r'^bio/(?P<username>\w+)/$', views.bio, name='bio'),
# -----
r'' : re module(Regular expression operations)
^ : Matches the start of the string, 在[]中表否定
(?P<name>...) : Group names must be valid Python identifiers
+ : Causes the resulting RE to match 0 or more repetitions of the preceding RE
\d : Matches any Unicode decimal digit, If the ASCII flag is used only [0-9] is matched.
\w : Matches Unicode word characters, If the ASCII flag is used, only [a-zA-Z0-9_] is matched.
$ : Matches the end of the string or just before the newline at the end of the string, foo matches both ‘foo’ and ‘foobar’, foo$ matches only ‘foo’
. : 任何字元都符合
\D : 非數字0~9
\W : [a-zA-Z0-9_]  
* : 出現 0 or 0 次以上
+ : 出現 1 or 1 次以上
? : 出現 0 or 1 次 
| : 任一種符合都可以
(...) : 若符合,則取出成為一個參數
[...] : 表示一個字元的格式
{m} : 代表前一個字,可出現m次
{m,n} : 代表前一個字,可出現m到n次
# path ----
path(route, view, kwargs=None, name=None)
path('index/', views.index, name='main-view'),
path('bio/<username>/', views.bio, name='bio'),
path('weblog/', include('blog.urls')),
# re_path ----
re_path(route, view, kwargs=None, name=None)
re_path(r'^index/$', views.index, name='index'),
re_path(r'^bio/(?P<username>\w+)/$', views.bio, name='bio'),
re_path(r'^weblog/', include('blog.urls')),
```

* **[Request and response objects](https://docs.djangoproject.com/en/2.2/ref/request-response/#django.http.HttpResponse)**  
HttpResponse  
```python
from django.http import HttpResponse
response = HttpResponse("Here's the text of the Web page.")
response = HttpResponse("Text only, please.", content_type="text/plain")
response = HttpResponse(b'Bytestrings are also accepted.')
HttpResponse("you're looking at question %s." % question_id)
# 2nd sample
from django.template import loader
from django.http import HttpResponse
def index(request):
  latest_question_list = Question.objects.order_by('-pub_date')[:5]
  template = loader.get_template('polls/index.html')
  content = {
      'latest_question_list' : latest_question_list,
  }
  return HttpResponse(template.render(content, request))
```

* **[Django shortcut functions](https://docs.djangoproject.com/en/2.2/topics/http/shortcuts/)**  
render  
render(request, template_name, context=None, content_type=None, status=None, using=None)  
```python
from django.shortcuts import render
def my_view(request):
    # View code here...
    return render(request, 'myapp/index.html', {
        'foo': 'bar',
    }, content_type='application/xhtml+xml')
```

* **some commad**
	* show models migrate record  
	python manage.py sqlmigrate mainsite 0001  
	python manage.py sqlmigrate mainsite 0002  

## .web side  
* [imgur-圖片上傳空間](https://imgur.com/)





