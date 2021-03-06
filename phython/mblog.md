## [Python Guide](./python_guide.md)

## mblog
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

