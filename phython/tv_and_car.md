## [Python Guide](./python_guide.md)

## TV and Car

* **simple 1st**  
	* create project and app  
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

	* tvs urls  
	tvs/urls.py  
	```python
	from django.urls import path, re_path
	from . import views
	urlpatterns = [
		path('', views.home ),
		path('tvs/index', views.index ),
	]
	```

	* car urls  
	car/urls.py  
	```python
	from django.urls import path, re_path
	from . import views
	urlpatterns = [
		path('index', views.index ),
	]
	```

	* tvs views  
	tvs/views.py  
	```python
	from django.shortcuts import render
	from django.http import HttpResponse
	def home(request):
		return HttpResponse("home...")
	def index(request):
		return HttpResponse("tvs index...")
	```

	* car views  
	car/views.py  
	```python
	from django.shortcuts import render
	from django.http import HttpResponse
	def index(request):
		return HttpResponse("card index...")
	```

	* run server  
	python manage.py runserver  
	http://127.0.0.1:8000/  
	http://127.0.0.1:8000/tvs/index  
	http://127.0.0.1:8000/car/index  
	http://127.0.0.1:8000/admin  

* **add chinese news channel and english news channelt**  
	* channel embedded link  
	```html
	台視 <iframe width="560" height="315" src="https://www.youtube.com/embed/NbjI0cARzjQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	民視 <iframe width="560" height="315" src="https://www.youtube.com/embed/XxJKnDLYZz4" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	中天 <iframe width="560" height="315" src="https://www.youtube.com/embed/wUPPkSANpyo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	東森 <iframe width="560" height="315" src="https://www.youtube.com/embed/RaIJ767Bj_M" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	Sky <iframe width="560" height="315" src="https://www.youtube.com/embed/zg_YUu2JzEA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	ABC <iframe width="560" height="315" src="https://www.youtube.com/embed/nu3iXDR7iXo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	DW <iframe width="560" height="315" src="https://www.youtube.com/embed/NvqKZHpKs-g" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	```

	* system setting  
	tvacar/settings.py  
	add root template  
	```python
	TEMPLATES = [
	    {
	        'BACKEND': 'django.template.backends.django.DjangoTemplates',
	        # add project templates
	        'DIRS': [os.path.join(BASE_DIR, 'templates')],
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

	* tvs urls  
	tvs/urls.py  
	```python
	urlpatterns = [
		path('', views.home ),
		path('tvs/index/', views.index , name="index"),
		re_path(r'^tvs/index/(?P<tvindex>\d*)/$', views.index, name="index_n"),
		path('tveng/index/', views.tveng , name="tveng"),
		re_path(r'^tveng/index/(?P<tvindex>\d*)/$', views.tveng, name="tveng_n"),
	]
	```

	* tvs views  
	tvs/views.py  
	```python
	from django.shortcuts import render
	from django.http import HttpResponse
	from datetime import datetime
	from django.template.loader import get_template
	def home(request):
		return render(request, "home.html")
	def index(request,tvindex='0'):
		# cannot include dict
		#tv_list = [
		#	{'name':'台視', 'tvcode':'NbjI0cARzjQ'},
		#	{'name':'民視', 'tvcode':'XxJKnDLYZz4'},
		#	{'name':'中天', 'tvcode':'wUPPkSANpyo'},
		#	{'name':'東森', 'tvcode':'RaIJ767Bj_M'},
		#]
		tvs_name = ['台視', '民視', '中天', '東森']
		tvs_code = ['NbjI0cARzjQ', 'XxJKnDLYZz4', 'wUPPkSANpyo', 'RaIJ767Bj_M']
		now = datetime.now()
		tvindex = int(tvindex)
		tvno = len(tvs_name)
		# cannot include dict
		#content = {
		#		#'tv_list' : tv_list,
		#		'tvs_name' : tvs_name,
		#		'tvs_code' : tvs_code,
	  #    'now' : now,
	  #    'tvno' : tvno,
	  #}
		#template = get_template("tvs/index.html")
		#html = template.render(content)
		#print(type(content))
		#return render(request, "tvs/index.html", content)
		return render(request, "tvs/index.html", locals())
	def tveng(request,tvindex='0'):
		tvs_name = ['Sky', 'ABC', 'DW']
		tvs_code = ['zg_YUu2JzEA', 'nu3iXDR7iXo', 'NvqKZHpKs-g']
		now = datetime.now()
		tvindex = int(tvindex)
		tvno = len(tvs_name)
		eng_mode = True
		return render(request, "tvs/index.html", locals())
	```

	* home template  
	template/home.html  
	```python
	<ul>
		<li>
			<a href="/tvs/index/">電視頻道</a>
		</li>
		<li>
			<a href="/tveng/index/">English Channel</a>
		</li>
		<li>
			<a href="/car/index/">車子</a>
		</li>
	</ul>
	```

	* car index template  
	car/template/index.html  
	```python
	<h1>car index</h1>
	```

	* add static image  
	tvs/static/images/flow.jpg  

	* tvs index template  
	tvs/template/index.html  
	```python
	<!--	index.html -->
	{% extends "tvs/base.html" %}
	{% block  title %}TV Home Page{% endblock %} 
	{% block content %}
		{% load mine %}
		{% load static %}
		<div class="container-fluid">
			<nav class="navbar navbar-expand-lg navbar-light bg-light">
				<img src="{% static 'images/flower.jpg' %}" alt="" height="64" width="64">
				<a class="navbar-brand" href="#">現正撥出{{ tvs_name|index:tvindex }}</a>
				<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
					<span class="navbar-toggler-icon"></span>
				</button>
				<div class="collapse navbar-collapse" id="navbarNav">
					<ul class="navbar-nav">
						<li class="nav-item mr-4">
							<a href="/">主頁</a>
						</li>
						{% for name in tvs_name %}
							<li class="nav-item mr-4">
								{% if eng_mode %}
									<a href="{% url 'tveng_n' forloop.counter0 %}">{{ name }}</a>
								{% else %}
									<a href="{% url 'index_n' forloop.counter0 %}">{{ name }}</a>
								{% endif %}
							</li>
						{% endfor %}
					</ul>
				</div>
			</nav>
		</div>
		<div class="container">
			<div id="tvcode" align='center'>
				<iframe width="560" height="315" src="https://www.youtube.com/embed/{{ tvs_code|index:tvindex }}?rel=0&amp;showinfo=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
			</div>
		</div>
		<div class="container-fluid bg-light">
			{{ now }}
		</div>
	{% endblock  %}
	```

	* tvs base template  
	tvs/template/base.html  
	```python
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
		{% include "tvs/header.html" %}
		{% block content %} {% endblock  %}
		{% include "tvs/footer.html" %}
	  <!-- Optional JavaScript -->
	  <!-- jQuery first, then Popper.js, then Bootstrap JS -->
	  <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
	  <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
	  <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
	</body>
	</html>
	```

	* tvs header template  
	tvs/template/header.html  
	```python
	<h1>TVS</h1>
	```

	* tvs footer template  
	tvs/template/footer.html  
	```python
	<p>tvs....</p>
	```

	* add templatetags  
	tvs/templatetags/__init__.py  
	tvs/templatetags/mine.py  
	```python
	from django import template
	register = template.Library()
	#@register.filter(name='cut')
	#def cut(value, arg):
	#    """Removes all values of arg from the given string"""
	#    return value.replace(arg, '')
	@register.filter(name='index')
	def index(indexable, i):
	    return indexable[i]
	```

	* run server  
	python manage.py runserver  
	http://127.0.0.1:8000/  
	http://127.0.0.1:8000/tvs/index/  
	http://127.0.0.1:8000/tveng/index/  
	http://127.0.0.1:8000/car/index/  

* **change template parameter using list**  
	* tvs views  
	tvs/views.py  
	```python
	def index(request,tvindex='0'):
		tv_list = [
			{'name':'台視', 'tvcode':'NbjI0cARzjQ'},
			{'name':'民視', 'tvcode':'XxJKnDLYZz4'},
			{'name':'中天', 'tvcode':'wUPPkSANpyo'},
			{'name':'東森', 'tvcode':'RaIJ767Bj_M'},
		]
		now = datetime.now()
		tvno = len(tv_list)
		tv = tv_list[int(tvindex)]
		return render(request, "tvs/index.html", locals())
	def tveng(request,tvindex='0'):
		tv_list = [
			{'name':'Sky', 'tvcode':'zg_YUu2JzEA'},
			{'name':'ABC', 'tvcode':'nu3iXDR7iXo'},
			{'name':'DW', 'tvcode':'NvqKZHpKs-g'},
		]
		now = datetime.now()
		tvno = len(tv_list)
		tv = tv_list[int(tvindex)]
		eng_mode = True
		return render(request, "tvs/index.html", locals())
	```

	* tvs index template  
	tvs/template/index.html  
	```python
	<!--	index.html -->
	{% extends "tvs/base.html" %}
	{% block  title %}TV Home Page{% endblock %} 
	{% block content %}
		{% load static %}
		<div class="container-fluid">
			<nav class="navbar navbar-expand-lg navbar-light bg-light">
				<img src="{% static 'images/flower.jpg' %}" alt="" height="64" width="64">
				<a class="navbar-brand" href="#">現正撥出{{ tv.name }}</a>
				<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
					<span class="navbar-toggler-icon"></span>
				</button>
				<div class="collapse navbar-collapse" id="navbarNav">
					<ul class="navbar-nav">
						<li class="nav-item mr-4">
							<a href="/">主頁</a>
						</li>
						{% for t in tv_list %}
							<li class="nav-item mr-4">
								{% if eng_mode %}
									<a href="{% url 'tveng_n' forloop.counter0 %}">{{ t.name }}</a>
								{% else %}
									<a href="{% url 'index_n' forloop.counter0 %}">{{ t.name }}</a>
								{% endif %}
							</li>
						{% endfor %}
					</ul>
				</div>
			</nav>
		</div>
		<div class="container">
			<div id="tvcode" align='center'>
				<iframe width="560" height="315" src="https://www.youtube.com/embed/{{ tv.tvcode }}?rel=0&amp;showinfo=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
			</div>
		</div>
		<div class="container-fluid bg-light">
			{{ now }}
		</div>
	{% endblock  %}
	```

* **add car app page information**  
	* home template  
	template/home.html  
	```python
	<ul>
		<li>
			<a href="/tvs/index/">電視頻道</a>
		</li>
		<li>
			<a href="/tveng/index/">English Channel</a>
		</li>
		<li>
			<a href="/car/list/">車子</a>
		</li>
	</ul>
	```

	* car urls  
	car/urls.py  
	```python
	from django.urls import path, re_path
	from . import views
	urlpatterns = [
		path('list/', views.list ),
		re_path(r'^list/(?P<makerindex>\d*)/$', views.list, name="carlist_url"),
	]
	```

	* car views  
	car/views.py  
	```python
	def list(request,makerindex='0'):
		car_maker = [ 'SAAB', 'Ford', 'Honda', 'Mazda', 'Nissan', 'Topyto']
		car_list = [ [],
							['Fiesta', 'Focus', 'Medeo', 'EccSport', 'Kuga', 'Mustang'],
							['Fit', 'Odyssey', 'CR-V', 'City', 'NXS'],
							['Mazda3', 'Mazda5', 'Mazda6', 'CX-3', 'C-5', 'MX-5'],
							['Tida', 'March', 'Livina', 'Sentra', 'Teana', 'X-Trail', 'Juke', 'Murano'],
							['Camry', 'Altis', 'Yaris', '86', 'Prius', 'Vios', 'RAV4', 'Wish'],
						]
		makerindex = int(makerindex)
		maker_name = car_maker[makerindex]
		cars = car_list[makerindex]
		return render(request, "car/list.html", locals())
	```

	* car base template  
	car/template/base.html  
	```python
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
		{% include "car/header.html" %}
		{% block content %} {% endblock  %}
	  <!-- Optional JavaScript -->
	  <!-- jQuery first, then Popper.js, then Bootstrap JS -->
	  <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
	  <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
	  <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
	</body>
	</html>
	```

	* car header template  
	car/template/header.html  
	```python
	<h1>歡迎光臨DJ二手車賣場</h1>
	```

	* car list template  
	car/template/list.html  
	```python
	<!--	list.html -->
	{% extends "car/base.html" %}
	{% block  title %}二手車賣場{% endblock %} 
	{% block content %}
		<div class="container-fluid">
			<nav class="navbar navbar-expand-lg navbar-light bg-light">
				<button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
					<span class="navbar-toggler-icon"></span>
				</button>
				<div class="collapse navbar-collapse" id="navbarNav">
					<ul class="navbar-nav">
						<li class="nav-item mr-4">
							<a href="/">主頁</a>
						</li>
						{% for maker in car_maker %}
							<li class="nav-item mr-4">
								<a href="{% url 'carlist_url' forloop.counter0 %}">{{ maker }}</a>
							</li>
						{% endfor %}
					</ul>
				</div>
			</nav>
			<table class="ml-2 mt-2" border=1 width=400 bgcolor="ccffcc">
				<thead>
					{% if cars %}
						<tr>
							<td>車廠</td>
							<td>車款</td>
						</tr>
					{% endif %}
				</thead>
				<tbody>
					{% for c in cars %}
						<tr>
							<td>{{maker_name}}</td>
							<td>{{c}}</td>
						</tr>
					{% empty %}
						<h3>車廠 {{ maker_name }} 目前無庫存</h3>
					{% endfor %}
				</tbody>
			</table>
		</div>
	{% endblock  %}
	```

	* run server  
	python manage.py runserver  
	http://127.0.0.1:8000/  
	http://127.0.0.1:8000/car/list/  

* **car app add price**  
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
	    # add humanize
	    'django.contrib.humanize',
	    #'tvs',
	    'tvs.apps.TvsConfig',
	    'car.apps.CarConfig',
	]
	```

	* car views  
	car/views.py  
	```python
	def list(request,makerindex='0'):
		car_maker = [ 'Ford', 'Honda', 'Mazda']
		car_list = [
					[ 	{'model':'Fiesta','price':203500}, 
						{'model':'Focus', 'price':605000}, 
						{'model':'Medeo', 'price':900000}, 
						{'model':'EccSport', 'price':4500000}, 
					],
					[	{'model':'Fit', 'price':150000}, 
						{'model':'Odyssey', 'price':4500000}, 
						{'model':'CR-V', 'price':12000000}, 
					],
					[	{'model':'Mazda3', 'price':329999}, 
						{'model':'Mazda5', 'price':603000}, 
						{'model':'Mazda6', 'price':850000}, 
					],
				]
		makerindex = int(makerindex)
		maker_name = car_maker[makerindex]
		cars = car_list[makerindex]
		return render(request, "car/list.html", locals())
	```

	* car list template  
	car/template/list.html  
	```html
	{% load humanize %}
	<table class="ml-2 mt-2" border=1 width=400 bgcolor="ccffcc">
		<thead>
			{% if cars %}
				<tr>
					<td>車廠</td>
					<td>車款</td>
					<td>車價</td>
				</tr>
			{% endif %}
		</thead>
		<tbody>
			{% for c in cars %}
				<tr>
					<td>{{maker_name}}</td>
					<td>{{c.model}}</td>
					<td align='right'>NT${{c.price | floatformat:2 | intcomma}}</td>
				</tr>
			{% empty %}
				<h3>車廠 {{ maker_name }} 目前無庫存</h3>
			{% endfor %}
		</tbody>
	</table>
	```

