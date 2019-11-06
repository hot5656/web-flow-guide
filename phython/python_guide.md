# Python Guide  
[Django project](#django_project)  
[Django reference](#django_ref)  
[Package install](#package_install)  
[Debug](#debug)  
[Django Command](./django_command.md)  
[Refference](#reference)  
[Issue](#django_issue)  
[Reference link](#ref_link)  

<a id="django_project"></a>
## Django project  [[Home]](#) 
*  [mblog](./mblog.md)
*  [中古手機專賣店](./second_phone.md)
*  [中古手機專賣店-MySQL](./second_phone_mysql.md)
*  [TV and Car](./tv_and_car.md)
*  [Form example](./form_ex.md)


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

<a id="debug"></a>
## Debug  [[Home]](#)  

* VS code rune debug  
	Python Interpreter  
	```
	Ctrl+Shift+P -->  Python: Select Interpreter  
	F5 --> Python --> Django  
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
	STATICFILES_FINDERS = [
	    'django.contrib.staticfiles.finders.FileSystemFinder',
	    'django.contrib.staticfiles.finders.AppDirectoriesFinder',
	    'sass_processor.finders.CssFinder',
	]

	# set SASS_PRECISION ( default 5)  
	SASS_PRECISION = 8

	# set STATIC_ROOT  
	STATIC_ROOT = os.path.join(BASE_DIR, 'common_static')
	# use SASS_PROCESSOR_ROOT also ok
	# SASS_PROCESSOR_ROOT = os.path.join(BASE_DIR,'common_static')
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

* sass processor no generate css  
非使用 .scss 使用 .css  


<a id="ref_link"></a>
## Reference link  [[Home]](#) 
* [imgur-圖片上傳空間](https://imgur.com/)  
* [django-sass-processor](https://github.com/jrief/django-sass-processor)  
* [Django documentation](https://docs.djangoproject.com/en/2.2/)