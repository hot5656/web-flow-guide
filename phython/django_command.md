## [Python Guide](./python_guide.md)

## Django Command

* VS code set for Django  
```python
{
	"emmet.includeLanguages": {"django-html": "html"},
	"python.linting.pylintArgs": [
		"--load-plugins=pylint_django"
	],
}
```

* create project and app  
```
django-admin startproject sellphoneqsl  
cd sellphoneqsl  
python manage.py startapp secondphone  
```

* system setting  
sellphoneqsl/settings.py  
```
# add app 
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    # add for app
    'secondphone.apps.SecondphoneConfig',
]
# set language and time zone
LANGUAGE_CODE = 'zh-Hant'
TIME_ZONE = 'Asia/Taipei'
```

* set for MySQL  
```
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


* check set up
```
python manage.py check
```

* app models  
	secondphone/models.py  
	ForeignKey : ref other table key  
	>	on_delete=models.CASCADE-被參照的物件被刪除尺物件也一併執行刪除  
		models.PROTECT:禁止刪除並產生一個 excption  
		models.SET_NULL:把外來鍵設定為null,規劃時此欄位要設定可接受null  
		models.SET_DEFAULT:把外來鍵設定為預設值,規劃時此欄位要設有預設值  
		models.DO_NOTHING:甚麼事都不做

	CharField : max_length-max filed length  
	URLField  
	TextField  
	DateTimeField : type date , auto_now=True(generate add)  auto_now_add=True(generate add while ypdate)  
	BooleanField : type Boolean  
	PositiveIntegerField : positve int  
	__str__(self) : return string  
	default : default value  
	verbose_name : 代用名, show at admin ui  

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

	```python
	from django.db import models

	class Mood(models.Model):
		status = models.CharField(max_length=10)
		def __str__(self):
			return self.status

	class Post(models.Model):
		mood = models.ForeignKey(Mood, on_delete=models.CASCADE)
		nickname = models.CharField(max_length=10, default='訪客')
		message = models.TextField(null=False)
		del_pass = models.CharField(max_length=10)
		pub_time = models.DateTimeField(auto_now=True)
		enable = models.BooleanField(default=False)
		def __str__(self):
			return self.nickname
	```

* register models  
secondphone/admin.py  
search_fields :設定搜尋欄位  
ordering :設定排序欄位  
```python
from django.contrib import admin
from .models import Product
# admin.site.register(Product)
class ProductAdmin(admin.ModelAdmin):
	list_display = ( 'pmodel', 'nickname', 'price' , 'year')
	search_fields = ('nickname',)
	ordering = ('-price',)
admin.site.register(Product, ProductAdmin)
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

* system urls  
	point to app's urls  
	```python
	from django.contrib import admin
	from django.urls import path, include
	urlpatterns = [
		path('', include('secondphone.urls')),
		path('admin/', admin.site.urls),
	]
	```

	no use app's urls  
	```python
	from django.contrib import admin
	from django.urls import path, re_path
	from trips.views import hello_world, home, post_detail

	urlpatterns = [
		path('admin/', admin.site.urls),
		path('hello/', hello_world),
		path('', home),
		re_path(r'^post/(?P<pk>\d+)/$', post_detail, name='post_detail'),
	]
```


* app urls  
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
	from .models import PPhoto  
	> 亦可寫成 from secondphone import models  
		使用 models.PPhoto  

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

	simple return string  
	```python
	from django.http import HttpResponse
	def  index(request):
		return HttpResponse("index...")
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
		<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" ntegrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
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
		<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" rossorigin="anonymous"></script>
		<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" ntegrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
		<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/JGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
	</body>
	</html>
	```

	template/second/detail.html  
	```html
	<!-- detail.html -->
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

* template tags  

	if else end  
	for in  
	if forloop.first  
	if forloop.last  
	empty : for no anthing  
	forloop.count : for index  
	|divisibleby:2 : 被2整除  
	```html
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
	```

* temprate variable  

	```html
	<!-- image from url -->
	<img src="{{ pic.url }}" alt="" width=350><br>
	<!-- image from static -->
	{% load static %}
	<img src="{% static 'images/flower.jpg' %}" alt="" height="64" width="64">
	<!-- extends html file -->
	{% extends "second/base.html" %}
	<!-- reserve block title and content position -->
	{% block title %} {% endblock  %}
	{% block content %} {% endblock  %}
	<!-- include app templates/second html file -->
	{% include "second/header.html" %}
		{% block content %} {% endblock  %}
	<!-- set block value file -->
	{% block  title %}中古機賣場{% endblock %} 
	<!-- DB value -->
	<h5 class="card-title mb-1">{{ product.nickname }}</h5>
	<!-- link -->
	<a href="detail/{{ p.id }}/">{{p.nickname}}</a>
	<!-- link reference urls.py name=post_detai -->
	<!-- urls.py : re_path(r'^post/(?P<pk>\d+)/$', post_detail, name='post_detail'), -->
	<a href="{% url 'post_detail' pk=post.pk %}">{{ post.title }}
	<!-- link reference one app polls's urls.py name=vote(sub code) -->
	<!-- link reference one app polls's urls.py name=detail -->
	<!-- urls.py : app_name = 'polls' -->
	<!--           path('<int:question_id>/vote/', views.vote, name='vote'), -->
	<!--           path('<int:pk>/', views.DetailView.as_view(), name='detail'), -->
	<form action="{% url 'polls:vote' question.id %}" method="post">
	<a href="{% url 'polls:detail' question.id %}">{{question.question_text}}/</a>
	<!-- DB over 2 table value, DB p, make-->
	{{p.pmodel.make.name}}
	<!-- loas css-->
	{% load static %}
	<link rel="stylesheet" type="text/css" href="{% static 'polls/style.css' %}">
	<!-- loas sass-->
	{% load sass_tags %}
	<link href="{% sass_src 'scss/style.scss' %}" rel="stylesheet" type="text/css" />
	<!-- comment -->
	{% comment "Optional note" %}
		<p>Commented out text with {{ create_date|date:"c" }}</p>
	{% endcomment %}
	<!-- cycle string : 1st 'row1' , 2nd 'row2', 3th 'row1'...-->
	{% for o in some_list %}
		<tr class="{% cycle 'row1' 'row2' %}">
			...
		</tr>
	{% endfor %}
	<!-- cycle variable -->
	{% for o in some_list %}
		<tr class="{% cycle rowvalue1 rowvalue2 %}">
			...
		</tr>
	{% endfor %}
	<!-- cycle disable auto-escaping(轉義內容 disabel) -->
	{% for o in some_list %}
		<tr class="{% autoescape off %}{% cycle rowvalue1 rowvalue2 %}{% endautoescape %}">
			...
		</tr>
	{% endfor %}
	<!-- cycle variable and string -->
	{% for o in some_list %}
		<tr class="{% cycle 'row1' rowvalue2 'row3' %}">
			...
		</tr>
	{% endfor %}
	<!-- cycle 引用下一個值 -->
	{% cycle 'row1' 'row2' as rowcolors %}
	<tr>
		<td class="{% cycle 'row1' 'row2' as rowcolors %}">...</td> 下次遇到 cycle 'row2' 代替 rowcolors  
		<td class="{{ rowcolors }}">...</td>
	</tr>
	<tr>
		<td class="{% cycle rowcolors %}">...</td>
		<td class="{{ rowcolors }}">...</td>
	</tr>
	to 
	<tr>
		<td class="row1">...</td>
		<td class="row1">...</td>
	</tr>
	<tr>
		<td class="row2">...</td>
		<td class="row2">...</td>
	</tr>
	<!-- cycle 隱藏 -->
	{% for obj in some_list %}
		{% cycle 'row1' 'row2' as rowcolors silent %}
		<tr class="{{ rowcolors }}">{% include "subtemplate.html" %}</tr>
	{% endfor %}
	to 
	{% cycle reset %}
	<!-- cycle reset -->
	You can use the resetcycle tag to make a {% cycle %} tag restart from its first value 
	```

	* filter  
	```htlm
	<!-- otutpt low case -->
	{% filter force_escape|lower %}
		This text will be HTML-escaped, and will appear in all lowercase.
	{% endfilter %}
	```

	* if  
	 operators ==, !=, <, >, <=, >=, in, not in, is, and is not  
	```htlm
	<!-- multiple -->
	{% if var1 %}
		{{ var1 }}
	{% elif var2 %}
		{{ var2 }}
	{% elif var3 %}
		{{ var3 }}
	{% endif %}
	<!-- Boolean operators -->
	{% if athlete_list and coach_list %}
	Both athletes and coaches are available.
	{% endif %}
	{% if not athlete_list %}
	There are no athletes.
	{% endif %}
	{% if athlete_list or coach_list %}
	There are some athletes or some coaches.
	{% endif %}
	{% if not athlete_list or coach_list %}
	There are no athletes or there are some coaches.
	{% endif %}
	{% if athlete_list and not coach_list %}
	There are some athletes and absolutely no coaches.
	{% endif %}
	<!-- Use of both and and or clauses within the same tag is allowed, with and having higher precedence than or -->
	{% if athlete_list and coach_list or cheerleader_list %}
	as -->  if (athlete_list and coach_list) or cheerleader_list
	<!-- in -->
	{% if "bc" in "abcdef" %}
		This appears since "bc" is a substring of "abcdef"
	{% endif %}
	{% if "hello" in greetings %}
		If greetings is a list or set, one element of which is the string
		"hello", this will appear.
	{% endif %}
	{% if user in users %}
		If users is a QuerySet, this will appear if user is an
		instance that belongs to the QuerySet.
	{% endif %}
	<!-- is -->
	{% if somevar is True %}
		This appears if and only if somevar is True.
	{% endif %}
	{% if somevar is None %}
		This appears if somevar is None, or if somevar is not found in the context.
	{% endif %}
	```

	* for  
	```html
	<!-- reverse for -->
	{% for obj in list reversed %}
	<!-- for 2 維  -->
	{% for x, y in points %}
		There is a point at {{ x }},{{ y }}
	{% endfor %}
	<!-- access dictionary  -->
	{% for key, value in data.items %}
		{{ key }}: {{ value }}
	{% endfor %}
	<!-- for's variable -->
	forloop.counter			: The current iteration of the loop (1-indexed)
	forloop.counter0		: The current iteration of the loop (0-indexed)
	forloop.revcounter	: The number of iterations from the end of the loop (1-indexed)
	forloop.revcounter0	: The number of iterations from the end of the loop (0-indexed)
	forloop.first	True	: if this is the first time through the loop
	forloop.last	True	: if this is the last time through the loop
	forloop.parentloop	: For nested loops, this is the loop surrounding the current one
	<!-- empty -->
	{% for athlete in athlete_list %}
		<li>{{ athlete.name }}</li>
	{% empty %}
		<li>Sorry, no athletes in this list.</li>
	{% endfor %}
	```

	* ifchanged  
	```html
	<!-- value change -->
	{% for date in days %}
		{% ifchanged %}<h3>{{ date|date:"F" }}</h3>{% endifchanged %}
		<a href="{{ date|date:"M/d"|lower }}/">{{ date|date:"j" }}</a>
	{% endfor %}
	<!-- more variable -->
	{% for date in days %}
		{% ifchanged date.date %} {{ date.date }} {% endifchanged %}
		{% ifchanged date.hour date.date %}
			{{ date.hour }}
		{% endifchanged %}
	{% endfor %}
	<!-- else -->
	{% for match in matches %}
		<div style="background-color:
		{% ifchanged match.ballot_id %}
			{% cycle "red" "blue" %}
		{% else %}
			gray
		{% endifchanged %}
		">{{ match }}</div>
	{% endfor %}
	```

	* now  
	Displays the current date and/or time, using a format according to the given string  
	DATE_FORMAT, DATETIME_FORMAT, SHORT_DATE_FORMAT or SHORT_DATETIME_FORMAT 
	```python
	It is {% now "jS F Y H:i" %}
	It is the {% now "jS \o\f F" %} : no show year
	It is {% now "SHORT_DATETIME_FORMAT" %}
	```

	* lorem  
	Displays random “lorem ipsum” Latin text  
	> count	 : A number (or variable) containing the number of paragraphs or words to generate (default is 1).  
		method : Either w for words, p for HTML paragraphs or b for plain-text paragraph blocks (default is b).  
		random : The word random, which if given, does not use the common paragraph (“Lorem ipsum dolor sit amet…”) when generating text.  
	```html
	{% lorem [count] [method] [random] %}
	{% lorem %} : output the common “lorem ipsum” paragraph.
	{% lorem 3 p %} : output the common “lorem ipsum” paragraph and two random paragraphs each wrapped in HTML <p> tags.
	{% lorem 2 w random %} : output two random Latin words.
	```

* Form  
	* html  
	label : 對應 input 之說明  
	id : maping label and input 
	name : 提供運算之名稱  
	method : 指定 form 執行 POST or GET  
	action : submit 後 資料要被送到哪裡,一般指定 PHP or JS 的一個函數,Django 只到要處理的網址即可  
	value : 指定 input 的 default 值  
	submit : input 之特殊元素,就是 "送出資料" 的按鈕, value 設定按鈕文字  
	reset : input 之特殊元素,就是 "清除表單所有輸入值" 的按鈕, value 設定按鈕文字  
	type="password" : 密碼輸入  
	```html
	<form name='my_form' action="/" method='GET'>
		<label for="user_id">Your ID:</label>
		<input id='user_id' type="text" name='user_id'>
		<label for="user_pass">Your Passwrod:</label>
		<input id='user_pass' type="password" name='user_pass'>
		<input type="submit" value='登入'>
		<input type="reset" value='清除重填'>
	</form>
	```

	* views process form  
	```html
	from django.template.loader import get_template
	from django.http import HttpResponse 

	def index(request):
		template = get_template('index.html')
		try :
			urid = request.GET['user_id']
			urpass = request.GET['user_pass']
		except:
			urid = None 
		if urid != None and  urpass == '12345':
			verified = True
		else :
			verified = False
		print(urid, verified)
		return HttpResponse( template.render(locals()))
	```

	* check form data  
	```html
	Your ID:{{ urid | default:"未輸入ID" }}<br>
	{% if verified %}
		<em>你通過驗證</em>	
	{% else %}
		<em>帳號或密碼錯誤</em>		
	{% endif %}
	```

	* 常用元件  
	```html
	<!-- 下拉式選單 select -->
	<br>
	<label for="first">最喜歡水果</label>
	<select name="first" id="first">
		<option value="0">Apple</option>
		<option value="1">Banana</option>
		<option value="2">Cherry</option>
	</select>
	<br>
	<!-- 單選按鈕 radio -->
	<!-- checked 表勾選 -->
	最喜歡顏色(單選)<br>
	<input type="radio" name='fcolor' value='Green' checked>Green<br>
	<input type="radio" name='fcolor' value='Blue'>Blue<br>
	<input type="radio" name='fcolor' value='Red'>Red<br>
	<input type="radio" name='fcolor' value='Black'>Black<br>
	<!-- 核取方塊(多選) checkbox-->
	<!-- checked 表勾選 -->
	最喜歡顏色(多選)<br>
	<input type="checkbox" name='fcolor' value='Green' checked>Green<br>
	<input type="checkbox" name='fcolor' value='Blue'>Blue<br>
	<input type="checkbox" name='fcolor' value='Red'>Red<br>
	<input type="checkbox" name='fcolor' value='Black'>Black<br>
	<!-- 隱藏欄位 hidden -->
	<input type="hidden" name='hidevalue' value='hidevalue'>
	<!-- 多列文字 textarea -->
	<textarea name="message" id="" cols=20 rows=5>
	Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quidem saepe facilis aut nobis libero accusamus quaerat quam labore similique dolorem quasi obcaeca optio sed, quos voluptatum explicabo consequatur iure quisquam?
	</textarea><br>
	<!-- 自定按紐 button -->
	<input type="button" value='Google' onclick ='localtion.href="https://google.com"'>
	```

	* form called by views command  
	```python
	urid = request.GET['user_id']
	# get checkbox 
	urfcolor = request.GET.getlist('cfcolor')
	```

* DB access  
```python
products = Product.objects.all()
product = Product.objects.get(id=id)
image = PPhoto.objects.filter(product=product)
posts = Post.objects.filter(enable=True).order_by('-pub_time')[:30]
postsub = posts.count() % 3
# save DB  
mood = Mood.objects.get(status=user_mood)
post = Post.objects.create( 
	mood = mood,
	nickname = user_id,
	del_pass = user_pass,
	message = user_post
	)
post.save()
```
