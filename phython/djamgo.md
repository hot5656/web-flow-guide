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















