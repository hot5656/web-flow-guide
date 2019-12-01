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

	no use app's urls-2  
	```python
	from django.contrib import admin
	from django.urls import path, re_path
	from mainapp.views import index

	urlpatterns = [
	    path('', index),
	    re_path(r'^(\d+)/(\w+)/$', index),
	    path('admin/', admin.site.urls),
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

	views-2  
	```pythom
	def index(request, pid=None, del_pass=None):
		template = get_template('index.html')
		
		moods = Mood.objects.all()
		posts = Post.objects.filter(enable=True).order_by('-pub_time')[:30]
		postsub = posts.count() % 3
		......
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
.objects.all()  
.objects.get(id=id)  
.objects.filter(product=product)  
.objects.create  
posts.count() - gist size  
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
# deleted DB record  
try:
	post = Post.objects.get(id=pid)
except :
	post = None
if post:
	if post.del_pass == del_pass:
		post.delete()
		message = '資料刪除成功'
	else:
		message = '密碼錯誤'
```

* icon  
	* font awesome 4  
	```css
	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
	<i class="fa fa-trash" aria-hidden="true"></i>
	```

* from GET  
	GET方法則能漂亮的提供一個查詢相同頁面的URL  
	* form html  
	```html
		<form name='my_form' action="/" method='GET'>
			<label for="">現在的心情:</label><br>
			{% for m in  moods %}
				<input type="radio" name='mood' value='{{ m.status }}'>{{ m.status }}
			{% endfor %}
			<br>
			<label for="message">心情留言板:</label><br>
			<textarea name="user_post" id="message" cols=80 rows=4></textarea><br>
			<label for="user_name">你的暱稱:</label>
			<input id='user_name' type="text" name='user_name'>
			<label for="user_pass">張貼/刪除密碼:</label>
			<input id='user_pass' type="password" name='user_pass'><br>
			<input type="submit" value='張貼'>
			<input type="reset" value='清除重填'>
		</form>
	```

	* views  
	```python
	from django.template.loader import get_template
	from django.http import HttpResponse 
	from django.template import RequestContext
	from .models import Mood
	from .models import Post
	from mainapp import forms
	#
	def index(request, pid=None, del_pass=None):
		template = get_template('index.html')
	#
		moods = Mood.objects.all()
		posts = Post.objects.filter(enable=True).order_by('-pub_time')[:30]
		postsub = posts.count() % 3
	#
		try :
			user_id   = request.GET['user_name']
			user_pass = request.GET['user_pass']
			user_post = request.GET['user_post']
			user_mood = request.GET['mood']
			if not user_id or not user_pass or not user_post :
				raise ValueError('empty string')
		except:
			user_id = None 
			message = '如要張貼訊息,每個欄位都要填...'
	#
		if del_pass and pid:
			try:
				post = Post.objects.get(id=pid)
			except :
				post = None
			if post:
				if post.del_pass == del_pass:
					post.delete()
					# 調整 row col 數
					posts = Post.objects.filter(enable=True).order_by('-pub_time')[:30]
					postsub = posts.count() % 3
					message = '資料刪除成功'
				else:
					message = '密碼錯誤'
		elif user_id != None :
			mood = Mood.objects.get(status=user_mood)
			post = Post.objects.create( 
				mood = mood,
				nickname = user_id,
				del_pass = user_pass,
				message = user_post
				)
			post.save()
			message = '輸入成功請記得你的編輯密碼,訊息經審查後才會張貼...'
		return HttpResponse( template.render(locals()))
	```

	* urls  
	```python
	from django.contrib import admin
	from django.urls import path, re_path
	from mainapp.views import index, listing, posting, contact
	#
	urlpatterns = [
	    path('', index),
	    path('list/', listing),
	    path('post/', posting),
	    path('contact/', contact),
	    re_path(r'^(\d+)/(\w+)/$', index),
	    path('admin/', admin.site.urls),
	]
	```

	* del html  
	```html
	<div class="card-footer text-right">{{ p.pub_time }}
		<span class="post_del" onclick=del_post({{ p.id }})><i class="fa fa-trash" aria-hidden="true"></i></span>
	</div>	
	```

	* del js  
	```js
	function del_post(id) {
		var user_pass = document.getElementById('user_pass').value
		if (user_pass!="") {
			var usr = '/' + id + '/' + user_pass;
			window.location = usr;
		}
		console.log("del_post")
	}
	```

* form POST  
	POST方法適合拿來做資訊需隱密的請求  
	* form html  
	```html
	<form name='my_form' action="." method='POST'>
	{% csrf_token %}
		<label for="">現在的心情:</label><br>
		{% for m in  moods %}
			<input type="radio" name='mood' value='{{ m.status }}'>{{ m.status }}
		{% endfor %}
		<br>
		<label for="message">心情留言板:</label><br>
		<textarea name="user_post" id="message" cols=80 rows=4></textarea><br>
		<label for="user_name">你的暱稱:</label>
		<input id='user_name' type="text" name='user_name'>
		<label for="user_pass">張貼/刪除密碼:</label>
		<input id='user_pass' type="password" name='user_pass'><br>
		<input type="submit" value='張貼'>
		<input type="reset" value='清除重填'>
	</form>
	```

	* views  
	```python
	def posting(request):
		template = get_template('posting.html')
		moods = Mood.objects.all()
		if request.method == "POST":
			try :
				user_id   = request.POST['user_name']
				user_pass = request.POST['user_pass']
				user_post = request.POST['user_post']
				user_mood = request.POST['mood']
				if not user_id or not user_pass or not user_post :
					raise ValueError('empty string')
			except:
				user_id = None 
				message = '如要張貼訊息,每個欄位都要填...'
	#
			if user_id != None :
				mood = Mood.objects.get(status=user_mood)
				post = Post.objects.create( 
					mood = mood,
					nickname = user_id,
					del_pass = user_pass,
					message = user_post
					)
				post.save()
				message = '輸入成功請記得你的編輯密碼,訊息經審查後才會張貼...'
		else :
			message = '請張貼訊息...'
	#
		html = template.render(context=locals(), request=request)
		return HttpResponse(html)
	```

	* urls  
	```python
	urlpatterns = [
		path('post/', posting),
	]
	```


* Django Form  
	* form'py(forms.py)  
	```python
	from django import forms
	#
	class ContactForm(forms.Form) :
		CITY = [
			['TP', 'Taipei'],
			['TY', 'Taiyuang'],
			['TC', 'Taichung'],
			['TN', 'Tainan'],
			['KS', 'Kaoshiung'],
			['NA', 'Others'],
		]
	#
		user_name = forms.CharField( label='你的姓名', max_length=50, initial='李大仁')
		user_city = forms.ChoiceField( label='居住城市', choices=CITY)
		user_school = forms.BooleanField( label='是否在學', required=False)
		user_email = forms.EmailField(label='電子郵件' )
		user_message = forms.CharField(label='你的意見', widget=forms.Textarea)
	```

	* html  
	form 可選格式 {{ form.as_p }}, {{ form.as_table }}, {{ form.as_ul }}  
	若選 {{ form.as_table }} 要加 < table>< /table>  
	```html
	<div class="container-fluid">
		{% if message %}
			<p class='bg-warning p-3 mt-3'>{{ message }}</p>
			{{ user_name }}<br>
			{{ user_city }}<br>
			{{ user_school }}<br>
			{{ user_email }}<br>
			{{ user_message }}<br>
		{% endif %}
	<!-- -->
		<div class="card">
			<div class="card-header">
				<form name="my form" action='.' method='POST'>
				{% csrf_token %}
				<h3>寫信給管理員</h3>
			</div>
			<div class="crad-body">
				<!--
				{{ form.as_p }}
				-->
				<table>
					{{ form.as_table }}
				</table>
				<!--
				{{ form.as_ul }}
				-->
			</div>
			<div class="card footer">
				<input type="submit" value='送出'>
				</form>
			</div>
		</div>
	</div>
	```

	* views  
	```python
	# forms
	from mainapp import forms
	def contact(request):
		if request.method == 'POST' :
			form = forms.ContactForm(request.POST)
			if form.is_valid() :
				message = '感謝你的來信.'
				# 取出資料
				user_name = form.cleaned_data['user_name']
				user_city = form.cleaned_data['user_city']
				user_school = form.cleaned_data['user_school']
				user_email = form.cleaned_data['user_email']
				user_message = form.cleaned_data['user_message']
			else :
				message = '請檢查輸日是否正確!'
		else :
			form = forms.ContactForm()
	#
		template = get_template('contact.html')
		html = template.render(context=locals(), request=request)
		return HttpResponse(html)
	```

	* urls  
	```python
	urlpatterns = [
		path('contact/', contact),
	]
	```

* send mail by mailgun  
	sandbox need to add Authorized Recipients and verified  
	* install django-mailgun  
	```
	pip install django-mailgun
	```

	* setting.py-SMPT  
	```
	# mailgun send mail -SMTP 
	EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
	EMAIL_HOST = 'smtp.mailgun.org'
	EMAIL_USE_TLS = True
	EMAIL_PORT = 587
	EMAIL_HOST_USER = 'postmaster@sandbox0fd01b2ae4cxx44ae8835131a053f97dcc.mailgun.org'
	EMAIL_HOST_PASSWORD = 'ee2ba59a112f89ae45ed813b2xx0c795ea-09001d55-8de0f963'
	```

	* views.py-SMPT  
	```python
	# mailjet/mailgun send mail-SMTP
	send_mail('Subject here_02', 'Here is the message.02', 'kyp001@gmail.com',
			['kyp001@yahoo.com.tw'], fail_silently=False)
	```

	* setting.py-API  
	```python
	# mailgun send mail-API 
	EMAIL_BACKEND = 'django_mailgun.MailgunBackend'
	MAILGUN_ACCESS_KEY = 'key-4476f02b6033178xx53837efb7ef39bc6c'
	MAILGUN_SERVER_NAME = 'sandbox0fd01b2ae4cxx44ae8835131a053f97dcc.mailgun.org'
	```

	* views.py-API  
	```python
	# mailgun send mail-API
	from django.core.mail import EmailMessage
	mail_body=u'''
			网友姓名：{}
			居住城市：{}
			是否在学校：{}
			反馈意见：{}
			'''.format(user_name,user_city,user_school,user_message)
	email=EmailMessage('Form ex 網友意見',
			mail_body,
			'kyp001@gmail.com',
			[user_email])#接受邮件的邮箱地址
	email.send()
	```

* send mail by mailjet  
	* install  
	```
	pip install django-mailjet
	```

	* setting.py-SMPT  
	```python
	# mailjet send mail -SMTP 
	EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
	EMAIL_HOST = 'in-v3.mailjet.com'
	EMAIL_USE_TLS = True
	# or 465
	EMAIL_PORT = 587
	EMAIL_HOST_USER = '34f724e77da918cxxf1cf2c0025a11bcf0'
	EMAIL_HOST_PASSWORD = '0ca36a1a154xxb1e8eb901290b052ebe46'
	```

	* views.py-SMPT  
	```python
	# mailjet send mail-SMTP
	send_mail('Subject here10', 'Here is the message.9', 'kyp001@gmail.com',
 			['kyp001@yahoo.com.tw'], fail_silently=False)
	```

	* setting.py-API  
	```python
	# mailjet send mail-API
	EMAIL_BACKEND = 'django_mailjet.backends.MailjetBackend'
	MAILJET_API_KEY = '34f724e77da918cxxf1cf2c0025a11bcf0'
	MAILJET_API_SECRET = '0ca36a1a154xxb1e8eb901290b052ebe46'
	```

	* views.py-API  
	```python
	# get variable from setting
	from django.conf import settings
	# send mail-SMTP
	from django.core.mail import send_mail
	# mail API
	from mailjet_rest import Client
	api_key =  settings.MAILJET_API_KEY
	api_secret = settings.MAILJET_API_SECRET
	mailjet = Client(auth=(api_key, api_secret), version='v3.1')
	data = {
	'Messages': [
					{
							"From": {
									"Email": "kyp001@gmail.com",
									"Name": "Mailjet Pilot"
							},
							"To": [
									{
											"Email": "kyp001@yahoo.com.tw",
											"Name": "passenger 1"
									}
							],
							"Subject": "Your email flight plan!_2",
							"TextPart": "Dear passenger 1, welcome to Mailjet! May the delivery force be with you!",
							"HTMLPart": "<h3>Dear passenger 1, welcome to <a href='https://www.mailjet.com/'>Mailjet</a>!</h3><br />May the delivery force be with you!"
					}
			]
	}
	result = mailjet.send.create(data=data)
	# print(result.status_code)
	# print(result.json())
	```

	```python
	# get variable from setting
	from django.conf import settings
	# send mail
	from django.core.mail import send_mail
	# mailjet send mail-API
	from mailjet_rest import Client
	api_key =  settings.MAILJET_API_KEY
	api_secret = settings.MAILJET_API_SECRET
	mailjet = Client(auth=(api_key, api_secret), version='v3.1')
	data = {
	'Messages': [
					{
							"From": {
									"Email": "kyp001@gmail.com",
									"Name": "Mailjet Pilot"
							},
							"To": [
									{
											"Email": "kyp001@yahoo.com.tw",
											"Name": "passenger 1"
									}
							],
							"Subject": "Your email flight plan!_5",
							"TextPart": "Dear passenger 1, welcome to Mailjet! May the delivery force be with you!",
							"HTMLPart": "<h3>Dear passenger 1, welcome to <a href='https://www.mailjet.com/'>Mailjet</a>!</h3><br />May the delivery force be with you!"
					}
			]
	}
	data['Messages'][0]['To'][0]['Name'] = user_name
	data['Messages'][0]['To'][0]['Email'] = user_email
	data['Messages'][0]['Subject'] = 'Form ex 網友意見'
	data['Messages'][0]['TextPart'] = '網友姓名:{}\n 居住城市:{}\n 是否在學:{}\n 反映意見:\n {}'.format(user_name, user_city, user_school, user_message) 
	data['Messages'][0]['HTMLPart'] = ''
	result = mailjet.send.create(data=data)
	```

* Model Form  
	* urls  
	```python
	from mainapp.views import index, listing, posting, contact, post2db
	# modelForm
	path('post2db/', post2db),
	```

	* form.py
	```python
	# add model form
	from .models import Post
	#add model form
	class PostForm(forms.ModelForm):
		class Meta :
			# reference models
			model = Post
			# access field
			fields = [ 'mood', 'nickname', 'message', 'del_pass']
	#
		def __init__(self, *args, **kwarges ):
			super(PostForm, self).__init__(*args, **kwarges )
			self.fields['mood'].label = '現在心情'
			self.fields['nickname'].label = '你的暱稱'
			self.fields['message'].label = '心情留言'
			self.fields['del_pass'].label = '設定密碼'
	```

	* views
	```python
	def post2db(request):
		template = get_template('post2db.html')
		# form type
		post_form = forms.PostForm()
		moods = Mood.objects.all()
		message = '如要張貼,每一欄位都要填.....'
		html = template.render(context=locals(), request=request)
		return HttpResponse(html)
	```

	* html(post2db.html)  
	```html
	<!-- post2db.html -->
	{% extends "base.html" %}
	{% block  title %}Post2DB{% endblock %} 
	{% block content %}
		<div class="container-fluid">
			{% if message %}
				<p class='bg-warning p-3 mt-3'>{{ message }}</p>
			{% endif %}
			<form name='my form' action="." method='POST'>
				{% csrf_token %}
				<table>
				{{ post_form.as_table }}
				</table>
				<input type="submit" value='張貼'>
				<input type="reset" value='清除重填'>
			</form>
		</div>
	{% endblock  %}
	```

	* views-check input then save  
	```python
	def post2db(request):
		if request.method == "POST":
			post_form = forms.PostForm(request.POST)
			if post_form.is_valid():
				message = '輸入成功請記得你的編輯密碼,訊息經審查後才會張貼...'
				# save DB
				post_form.save()
			else:
				message = '如要張貼訊息,每個欄位都要填...'
		else:
			# form type
			post_form = forms.PostForm()
			message = '如要張貼,每一欄位都要填.....'
		#
		template = get_template('post2db.html')
		moods = Mood.objects.all()
		html = template.render(context=locals(), request=request)
		return HttpResponse(html)
	```

* 防機器人驗證機制
	* install package - make sure pillow also installed  
	```
	pip install django-simple-captcha  
	```

	* setting.py  
	```python
	INSTALLED_APPS = [
		....
		# django-simple-captcha
		'captcha',
	]
	...
	# django-simple-captcha
	# django_simple_captcha 驗證碼配置其他配置項檢視文件
	# 預設格式
	CAPTCHA_OUTPUT_FORMAT = '%(image)s %(text_field)s %(hidden_field)s '
	CAPTCHA_NOISE_FUNCTIONS = ('captcha.helpers.noise_null', # 沒有樣式
	# 'captcha.helpers.noise_arcs', # 線
	# 'captcha.helpers.noise_dots', # 點
	)
	# 圖片中的文字為隨機英文字母，如 mdsh
	# CAPTCHA_CHALLENGE_FUNCT = 'captcha.helpers.random_char_challenge'
	# 圖片中的文字為數字表示式，如2 2=
	CAPTCHA_CHALLENGE_FUNCT = 'captcha.helpers.math_challenge' 
	# 超時(minutes)
	# CAPTCHA_TIMEOUT = 1 
	```

	* urls.py  
	```python
	# django-simple-captcha
	from django.urls import path, re_path, include
	urlpatterns = [
		....
		# django-simple-captcha
		path('captcha/', include('captcha.urls')),
	]
	```

	* form.py  
	```python
	# django-simple-captcha
	from captcha.fields import CaptchaField
	# django-simple-captcha(for model form)
	self.fields['captcha'].label = '確定你不是機器人'
	```

	* .html  
	```html
	{{ form.captcha }}
	```

