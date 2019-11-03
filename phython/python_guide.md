# Python Guide  
[Django project](#django_project)  
[Django reference](#django_ref)  
[Package install](#package_install)  
[Command](#command)  
[Refference](#reference)  
[Issue](#django_issue)  
[Reference link](#ref_link)  

<a id="django_project"></a>
## Django project  [[Home]](#) 
*  [mblog](./mblog.md)
*  [中古手機專賣店](./second_phone.md)
*  [中古手機專賣店-MySQL](./second_phone_mysql.md)
*  [TV and Car](./tv_and_car.md)


<a id="django_ref"></a>
## Django reference  [[Home]](#) 
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
# include all variable : locals()
def tveng(request,tvindex='0'):
	tvs_name = ['Sky', 'ABC', 'DW']
	tvs_code = ['zg_YUu2JzEA', 'nu3iXDR7iXo', 'NvqKZHpKs-g']
	now = datetime.now()
	tvindex = int(tvindex)
	tvno = len(tvs_name)
	eng_mode = True
	return render(request, "tvs/index.html", locals())
```

* **[Custom template tags and filters](https://docs.djangoproject.com/en/2.2/howto/custom-template-tags/)**  
```
create templatetags directory(app) - templatetags
add __init_.py
```
add templatetags file - ex: mine.py
```python
from django import template
register = template.Library()
@register.filter(name='index')
def index(indexable, i):
    return indexable[i]
```
template add load templatetags  
```html
{% load mine %}
<p>{{ tvs_code|index:tvindex }}</p>
```

* **Django template**  
[[The Django template language]](https://docs.djangoproject.com/en/2.2/ref/templates/language/)  
[[Built-in template tags and filters]](https://docs.djangoproject.com/en/2.2/ref/templates/builtins/)  
extened by base.html  
```html
{% extends "base_generic.html" %}
{% block title %}{{ section.title }}{% endblock %}
{% block content %}
<h1>{{ section.title }}</h1>
{% for story in story_list %}
<h2>
  <a href="{{ story.get_absolute_url }}">
    {{ story.headline|upper }}
  </a>
</h2>
<p>{{ story.tease|truncatewords:"100" }}</p>
{% endfor %}
{% endblock %}
```

some specific  

Variable   |Description
-----------|----------
forloop.counter		|The current iteration of the loop (1-indexed)
forloop.counter0	|The current iteration of the loop (0-indexed)
forloop.revcounter	|The number of iterations from the end of the loop (1-indexed)
forloop.revcounter0	|The number of iterations from the end of the loop (0-indexed)
forloop.first		|True if this is the first time through the loop
forloop.last		|True if this is the last time through the loop
forloop.parentloop	|For nested loops, this is the loop surrounding the current one

some filter  

過濾器名稱   |用法		|範例
-------------|----------|----------
capfirst|字首加大寫		|{{msg｜capfirst}}
addslashes |為字串加跳脫字元	|{{msg｜addslashes}} "it's a cat" to "it\'s a cat"
capfirst|字首加大寫		|{{msg｜capfirst}}
center,ljust,rjust|字串加上指定空格後對齊		|{{msg｜center:"15"}}
cut|移除指定子字串		|{{msg｜cut:" "}}清除空白
data|設定日期顯示格式		|{{value｜date:"D d M Y"}}
default|如果沒有值,使用預設值		|{{msg｜default:"沒有訊息"}}
dictsort|為字典格式排列順序		|{{value｜dictsort:"name"}}
dictsortreversed|上例反向排列 		|
divisibleby|測試是否可被指定數值整除	|{{value｜divisibleby:5}}
escape|把字串中HTML變成顯示字串	|{{msg｜escape}}
filesizeformat|顯示檔案大小格式KB,MB...	|{{value｜filesizeformat}}
first|取出list第一個	|{{value｜irst}}
last|取出list最後一個	|{{value｜last}}
length|傳回string長度	|{{value｜length}}
length_is|測試資料是否為指定長度	|{{value｜length_is:"3"}}
floatformat|指定浮點格式顯示資料	|{{value｜floatformat:"3"}}3位小數
linebreaks|把文字內容換行資料轉換成</br>+<p></p>|{{msg｜linebreaks}}
linebreaksbr|把文字內容換行資料轉換成</br>	|{{msg｜linebreaksbr}}
linenumber|顯示文字加上行號	|{{msg｜linenumber}}
lower/upper|字串轉匯微小寫/大寫	|{{msg｜linebreaksbr}}
random|以亂數把前面內容擇一顯示	|{{value｜lower}}
safe|標記字串為安全,不再處理跳脫字元	|{{msg｜safe}}
slugly|把字串空格變成'-',讓字串可安全放在網址上	|{{msg｜slugly}}
striptags|移除所有HTML標記	|{{msg｜striptags}}
truncatechars|裁切成指定長度,並把最後3字元改為...	|{{msg｜truncatechars:12}}
wordcount|計算字數	|{{msg｜wordcount}}
yesno|依內容是True,false,None顯示有以意義內容	|{{value｜yesno:"是,否,可能吧"}}

lorem  
```html
{% lorem [count] [method] [random] %}  
count  : 數量
method : w-文字, p-段落
random : 有加即為亂數產生
ex:
  {% lorem %}
  {% lorem 3 p %}
  {% lorem 2 w random %}
```

* **human touch**  
[django.contrib.humanize](https://docs.djangoproject.com/en/2.2/ref/contrib/humanize/)  
```python
#  INSTALLED_APPS 
'django.contrib.humanize'
# template 
{% load humanize %}
apnumber - 1 becomes one, 10 becomes 10
intcomma - 45000 becomes 45,000
intword - 1200000 becomes 1.2 million, 1200000000 becomes 1.2 billion 
naturalday - 16 Feb 2007 becomes yesterday, 17 Feb 2007 becomes today 
naturaltime - 17 Feb 2007 16:30:00 becomes now, 17 Feb 2007 16:29:31 becomes 29 seconds ago 
ordinal - 1 becomes 1st.
```

* **some commad**
	* show models migrate record  
	```
	python manage.py sqlmigrate mainsite 0001  
	python manage.py sqlmigrate mainsite 0002  
	```

<a id="package_install"></a>
## package install  [[Home]](#) 

* **mysqlclient**  
for link MySQL  
```
conda install mysqlclient  
```



<a id="command"></a>
## Command  [[Home]](#) 

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
TIME_ZONE = 'Asia/Taipei
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
```python
from django.contrib import admin
from django.urls import path, include
urlpatterns = [
	path('', include('secondphone.urls')),
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
	```




<a id="reference"></a>
## Refference  [[Home]](#) 

* sass  
	* django-compressor install by conda  
	conda install django-compressor
	> conda can not inclue the package 

	* pip install django-compressor  
	pip install django-compressor  
	> Failed building wheel for rcssmin

	* complet django-compressor install  
	pip install rcssmin --install-option="--without-c-extensions"  
	pip install rjsmin  
	pip install libsass django-compressor django-sass-processor  

	* set settings.py  

	```python
	# set sass_processor
	INSTALLED_APPS = [
	    ...
	    'sass_processor',
	    ...
	]

	# set STATICFILES_FINDERS
	STATICFILES_FINDERS = (
	    'django.contrib.staticfiles.finders.FileSystemFinder',
	    'django.contrib.staticfiles.finders.AppDirectoriesFinder',
	    'sass_processor.finders.CssFinder',
	)

	# set SASS_PRECISION ( default 5)  
	SASS_PRECISION = 8

	# set STATIC_ROOT  
	STATIC_ROOT = os.path.join(BASE_DIR, 'common_static')
	```

	* set Django templates

	```html
	{% load sass_tags %}
	<link href="{% sass_src 'scss/style.scss' %}" rel="stylesheet" type="text/css" />
	```

	* add scss file - example  
	app_dir\static\scss\style.scss 
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





<a id="django_issue"></a>
## Django issue  [[Home]](#) 

* TypeError: 'NoneType' object is not subscriptable  
似乎是DB server 回應太慢  
settings.py  
```py
DATA_UPLOAD_MAX_NUMBER_FIELDS = 1000
```


<a id="ref_link"></a>
## Reference link  [[Home]](#) 
* [imgur-圖片上傳空間](https://imgur.com/)  
* [django-sass-processor](https://github.com/jrief/django-sass-processor)  
* [Django documentation](https://docs.djangoproject.com/en/2.2/)