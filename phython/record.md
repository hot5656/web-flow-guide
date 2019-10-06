# phython record

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

## reference 
* **Machine Learning**  

涉及機率論、統計學、逼近論、凸分析、計算複雜性理論
> 機器學習想做的事情，簡單的說是要從資料中歸納出有用的規則。大數據說的是對大量的資料做分析，而人工智能說的是讓機器看起來更聰明，兩者都可以使用機器學習來做核心的工具  

監督式學習supervised learning(給予數據和標籤讓機器去學習)  
> 一個監督式學習者的任務在觀察完一些訓練範例（輸入和預期輸出）後，去預測這個函數對任何可能出現的輸入的值的輸出。  
  監督式學習就像是我們給了機器一堆貓的照片告訴機器說「這個是貓」，再給機器一堆狗的照片告訴它「這是狗」，讓機器自己去學習分辨，接著我們便能給予任何貓或狗的照片問機器讓機器告訴我們這是 貓 或 狗？

非監督式學習unsupervised learning(只給予數據沒有給予標籤)  
> 非監督式學習是一種機器學習的方式，並不需要人力來輸入標籤。它是監督式學習和強化學習等策略之外的一種選擇。在監督式學習中，典型的任務是分類和迴歸分析，且需要使用到人工預先準備好的範例(base)  
  非監督式學習就像是我們給了機器一堆貓的照片和一堆狗的照片，可是我們並沒有告訴機器說哪些是貓哪些是狗，要機器自己去學習判斷出分類出圖片的不同之處。

半監督式學習semi-supervised learning(結合監督式和非監督式)  
> 少部分資料有標準答案，可提供機器學習輸出時判斷誤差使用；大部分資料沒有標準答案，機器必須自己尋找答案。  
  我們任意選100張貓或狗的照片，在其中的10張告訴機器哪些是貓，哪些是狗，讓機器去學習認識貓與狗的外觀，再自己嘗試把另外90張照片內的特徵取出來進行分類。

增強學習(透過環境和經驗修正)  
> 人類在進行決策時，常常會根據目前「環境」 的「狀態」執行「動作」，執行動作會造成兩個結果：一是人們會得到「環境」給我們的回饋，也就是人類會得到「報酬」，接著我們所執行的動作也會去改變「環境」，使得「環境」進入到一個新的「狀態」，「觀察到目前的狀態->執行動作->收到報酬與觀察到新的狀態」的步驟，重複非常非常多次，直到某個終止時間。  
  和前面三種類型不同的地方在於，增強學習並不是一次給予全部資料先讓機器分類，而是不斷餵給機器資料，透過經驗讓機器不斷修正。



# Install package

## 1. install by pipe

* **upgrade pip**

```
python -m pip install --upgrade pip
```

* **jupyter notebook**

coding tool
```
pip install jupyter notebook
```

* **Python Requests**

對網路發動請求的套件，可實作對網頁做get、post等HTTP協定的行為
```
pip install requests
```

* **Python Beautifulsoup4**

借助網頁的結構特性來解析網頁的工具，只需要簡單的幾條指令就可以提取HTML標籤裡的元素
```
pip install beautifulsoup4
```

## 2. install in linux

* **python3**

```
// check install
apt list --installed | grep phython

// check version
python3 --version
```

* **Anaconda**

```
// web side
https://www.anaconda.com/distribution/

// get Bash script
cd temp
curl -O https://repo.anaconda.com/archive/Anaconda3-2019.07-Linux-x86_64.sh
// verify (md5 count)
md5sum Anaconda3-2019.07-Linux-x86_64.sh
// bash run
bash Anaconda3-2019.07-Linux-x86_64.sh
	...
	Do you approve the license terms? [yes|no] --> yes

	...
	[/home/sammy/anaconda3] >>>

	....
	Preparing transaction: done
	Executing transaction: \ WARNING conda.core.envs_manager:register_env(46): Unable to register environment. Path not writable or missing.
	  environment location: /home/robert/anaconda3
	  registry file: /home/robert/.conda/environments.txt
	done
	installation finished.
	Do you wish the installer to initialize Anaconda3
	by running conda init? [yes|no]
	[no] >>> --> yes
	no change     /home/robert/anaconda3/condabin/conda
	no change     /home/robert/anaconda3/bin/conda
	no change     /home/robert/anaconda3/bin/conda-env
	no change     /home/robert/anaconda3/bin/activate
	no change     /home/robert/anaconda3/bin/deactivate
	no change     /home/robert/anaconda3/etc/profile.d/conda.sh
	no change     /home/robert/anaconda3/etc/fish/conf.d/conda.fish
	no change     /home/robert/anaconda3/shell/condabin/Conda.psm1
	no change     /home/robert/anaconda3/shell/condabin/conda-hook.ps1
	no change     /home/robert/anaconda3/lib/python3.7/site-packages/xontrib/conda.xsh
	no change     /home/robert/anaconda3/etc/profile.d/conda.csh
	modified      /home/robert/.bashrc
	==> For changes to take effect, close and re-open your current shell. <==
	If you'd prefer that conda's base environment not be activated on startup, 
	   set the auto_activate_base parameter to false: 
	conda config --set auto_activate_base false
	Thank you for installing Anaconda3!
	===========================================================================
	Anaconda and JetBrains are working together to bring you Anaconda-powered
	environments tightly integrated in the PyCharm IDE.


// ==== just for reference ===
// 設置Anaconda環境
// conda create命令創建Anaconda環境。 例如，可以使用以下命令創建名為my_env的Python 3環境
conda create --name my_env python=3
// 激活新環境
source activate my_env
// =============================

// show token
jupyter notebook list  
```

* **crontab(環型工作排程)-linux comman**

|代表意義|分鐘|小時|日期|月份|週|指令|
|--------|----|----|----|----|---|----------|
|數字範圍|0-59|0-23|1-31|1-12|0-7|呀就指令啊|

特殊字符|代表意義
--------|----
*(星號)|代表任何時刻都接受的意思！舉例來說，範例一內那個日、月、週都是 * ， 就代表著『不論何月、何日的禮拜幾的 12:00 都執行後續指令』的意思！
,(逗號)|代表分隔時段的意思。舉例來說，如果要下達的工作是 3:00 與 6:00 時，就會是： 0 3,6 * * * command 時間參數還是有五欄，不過第二欄是 3,6 ，代表 3 與 6 都適用！
-(減號)|	代表一段時間範圍內，舉例來說， 8 點到 12 點之間的每小時的 20 分都進行一項工作： 20 8-12 * * * command 仔細看到第二欄變成 8-12 喔！代表 8,9,10,11,12 都適用的意思！
/n(斜線)|	那個 n 代表數字，亦即是『每隔 n 單位間隔』的意思，例如每五分鐘進行一次，則： */5 * * * * command 很簡單吧！用 * 與 /5 來搭配，也可以寫成 0-59/5 ，相同意思！
none|***

```
// 9:30 到 16:30 之間每小時都執行一次
crontab -e
30 9-16 * * * /home/ubuntu/miniconda3/bin/python /home/ubuntu/price_rank_scraper.py
```

## 3. Anaconda
```
// list install package
conda list

// install package
conda install pandas

// create  虛擬環境
conda create --name py3test python=3
// create new environment(include flask and panda)
conda create --name flask python=3 flask pandas
// active 
conda activate py3test
// deactive

//To activate this environment
conda activate py3test
//deactivate an active environment, use
conda deactivate
// show all environment
conda env list
// remove environment
conda remove --name myenv numpy

// install Django
conda install django
// check version 
python -m django --version
// quit python shell
Ctrl-D or exit


```

## 4. Miniconda(輕量化版本的 Anaconda)
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
// which python 檢視可以發現系統已經改以 Miniconda 的 Python 作為預設。
conda install requests beautifulsoup4 pandas
```

## 5. VsCode
```
// pylint(檢查 Python 程式碼)
python.exe -m pip install -U pylint --user

  WARNING: The script isort.exe is installed in 'C:\Users\RobertKao\AppData\Roaming\Python\Python37\Scripts' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
  Running setup.py install for wrapt ... done
  WARNING: The scripts epylint.exe, pylint.exe, pyreverse.exe and symilar.exe are installed in 'C:\Users\RobertKao\AppData\Roaming\Python\Python37\Scripts' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
Successfully installed astroid-2.2.5 isort-4.3.21 lazy-object-proxy-1.4.1 mccabe-0.6.1 pylint-2.3.1 typed-ast-1.4.0 wrapt-1.11.2
WARNING: You are using pip version 19.1.1, however version 19.2.1 is available.
You should consider upgrading via the 'python -m pip install --upgrade pip' command.

// select env
ctrl-shift-p --> Python: Select Interpreter

```

# Django(創建 Web 應用程式和 Web API 的框架)

## 1. 1st web page  
https://docs.djangoproject.com/en/2.2/intro/tutorial01/

* **create project**  
mkdir local  
cd local  
django-admin startproject mysite  
cd mysite  
```
mysite  
	mysite/
		settings.py
		urls.py
		wsgi.py
		__init__.py
	manage.py
```


* **run web server**  

python manage.py runserver  
web browse run : http://127.0.0.1:8000/  
python manage.py runserver 8080 - change port number  
python manage.py runserver ip:8080 - set ip for other host access  
> if found error 
  modify project_name/settings.py
  ```
  ALLOWED_HOSTS = ['*']
  ```

* **add app(pools)**  
	* python manage.py startapp polls  
	```python
	polls
		migrations/
			__init__.py
		admin.py
		apps.py
		migrations
		models.py
		tests.py
		views.py
		__init__.py
	```

	* Write your app view (polls/views.py)  

	```python
	from django.http import HttpResponse
	def index(request):
	    return HttpResponse("Hello, world. You're at the polls index.")
	```

	* map view to url(create polls/urls.py)  

	```python
	from django.urls import path

	from . import views

	urlpatterns = [
	    path('', views.index, name='index'),
	]
	```

	* point polls.urls to root(mysite/urls.py)

	```python
	from django.contrib import admin
	from django.urls import include, path

	urlpatterns = [
	    path('polls/', include('polls.urls')),
	    # if want to direct access
	    # path('', include('polls.urls')),
	    path('admin/', admin.site.urls),
	]
	```

* **run web server**  
python manage.py runserver  
web browse run : http://127.0.0.1:8000/  - Page not found  
web browse run : http://127.0.0.1:8000/polls/  - hello page  
web browse run : http://127.0.0.1:8000/admin/  - login page(name, password ??)  

* **create Django super user**  
	* migrate(1st time if need)  
	python manage.py migrate  
	* create super user(user:robert passwoed:robert)  
	python manage.py createsuperuser

## 2. girl Django
https://djangogirlstaipei.gitbooks.io/django-girls-taipei-tutorial/django/project_and_app.html  

* **create project**  
django-admin.py startproject demo_site  
cd demo_site  

* **run web server**  
python manage.py runserver  
python manage.py migrate - if need  

* **add app**  
python manage.py startapp trips  
demo_site/settings.py
```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'trips',
]
```

* Write your app view (trips/views.py)  
```
from django.http import HttpResponse
def hello_world(request):
    return HttpResponse("Hello World!")
```

* point root url to trips(demo_site/urls.py)
```
from django.contrib import admin
from django.urls import path
from trips.views import hello_world
urlpatterns = [
    path('admin/', admin.site.urls),
    path('hello/', hello_world),
]
```

* **run web server**  
python manage.py runserver  
web browse run : http://127.0.0.1:8000/hello/  - trips Page  

## 2.1 girl Django - add template 
* **change template directory**  
mkdir templates  
demo_site/settings.py  
```python
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        # kyp(2019/09/24) : change templates 
        #'DIRS': [],
        'DIRS': [os.path.join(BASE_DIR, 'templates').replace('\\', '/')],
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

* **add template file**

templates/hello_world.html  
```
  <em>{{ current_time }}</em>  
  {{<variable_name>}} 是在 Django Template 中顯示變數的語法。  
```
```html
<!-- hello_world.html -->

<!DOCTYPE html>
<html>
    <head>
        <title>I come from template!!</title>
        <style>
            body {
               background-color: lightyellow;
            }
            em {
                color: LightSeaGreen;
            }
        </style>
    </head>
    <body>
        <h1>Hello World!</h1>
        <em>{{ current_time }}</em>
    </body>
</html>
```

* modify view function(trips/views.py)  
```python
# trips/views.py
from datetime import datetime
from django.shortcuts import render
def hello_world(request):
    return render(request, 'hello_world.html', {
        'current_time': str(datetime.now()),
    })
```

* **run web server**  
python manage.py runserver  
web browse run : http://127.0.0.1:8000/hello/  - trips Page  

## 2.2 girl Django - models 
* **database setting**  
	demo_site/settings.py  
	```python
	DATABASES = {
	    'default': {
	        'ENGINE': 'django.db.backends.sqlite3',
	        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
	    }
	}
	```
	ENGINE -- 你要使用的資料庫引擎  
	> MySQL: django.db.backends.mysql
	  SQLite 3: django.db.backends.sqlite3
	  PostgreSQL: django.db.backends.postgresql_psycopg2  

	NAME -- 你的資料庫名稱

* **add models**  
	trips/models.py  
	宣告一個 Post 類別，並定義裡面的屬性，而 Django 會依據這個建立資料表，以及資料表裡的欄位設定  
	```python
	# trips/models.py
	from django.db import models
	# ------------------
	class Post(models.Model):
	    title = models.CharField(max_length=100)
	    content = models.TextField(blank=True)
	    photo = models.URLField(blank=True)
	    location = models.CharField(max_length=100)
	    created_at = models.DateTimeField(auto_now_add=True)
	```
	Django 預設會為每一個 Model 加上 id 欄位，並將這個欄位設成 primary key（主鍵），簡稱 pk，讓每一筆資料都會有一個獨一無二的 ID。  
	為 Post 定義以下屬性：  
	屬性		|資料型態		|說明		|參數
	--------	|-----			|-----		|----
	title		|CharField		|標題		|max_length=100 -- 標題不可以超過 100 個字元
	content		|TextField		|內文		|blank=True -- 非必填欄位（表單驗證時使用），預設所有欄位都是 blank=False
	photo		|URLField		|照片網址	|同 content，非必填欄位
	location	|CharField		|地點		|同 title
	created_at	|DateTimeField	|建立時間	|auto_now_add=True -- 物件新增的時間。若想設成物件修改時間，則用 auto_now=True

* **sync database**  
python manage.py makemigrations - 這個指令會根據你對 Model 的修改刪除建立一個新的 migration 檔案  
python manage.py migrate - 更新資料庫  

* **後台管理設定**  
	* demo_site/settings.py(已設定)  
	```python
	INSTALLED_APPS = [
	    'django.contrib.admin',
		...
	]
	```
	
	* demo_site/urls.py(已設定)  
	```python
	urlpatterns = [
	    path('admin/', admin.site.urls),
	]
	```
	
	* create super user  
	python manage.py createsuperuser
	
	* register model  
	trips/admin.py  
	```python
	from django.contrib import admin
	from .models import Post
	admin.site.register(Post)
	```

	* enter admin
	python manage.py runserver  
	http://127.0.0.1:8000/admin  

	* set return title(can see at administration)  
	trips/models.py  
	```python
	class Post(models.Model):
		.....
	    created_at = models.DateTimeField(auto_now_add=True)
	    def __str__(self):
	    	return self.title
	```
	python manage.py makemigrations - 這個指令會根據你對 Model 的修改刪除建立一個新的 migration 檔案  
	python manage.py migrate - 更新資料庫  
	python manage.py runserver  
	http://127.0.0.1:8000/admin  

## 2.3 girl Django - ORM(Object-relational mapping)  
CRUD 指的是，Create (新增)、Read (讀取)、Update (修改)、Delete (刪除) 等常見的資料庫操作  

* **Django Shell(加強版的 Python shell)**  
conda install ipython - install if not found  
python manage.py shell
```python
# Create 
from trips.models import Post
Post.objects.create(title='My First Trip', content='肚子好餓，吃什麼好呢?',  location='台北火車站') 
Post.objects.create(title='My Second Trip', content='去散散步吧',  location='大安森林公園')
Post.objects.create(title='Django 大冒險', content='從靜態到動態',  location='台北市大安區復興南路一段293號')
# ....
# Raed 
Post.objects.all()
# read - add get for filter
Post.objects.get(pk=1)
Post.objects.filter(location__contains='台北')
# ....
# Update 
posts = Post.objects.filter(title__contains='Trip')
posts
posts[0].location
posts[1].location
# update field
posts.update(location='象山親山步道')
posts[0].location
posts[1].location
# Delete
posts.delete()
Post.objects.all()
```
> get：返回符合條件的唯一一筆資料。（注意：如果找不到符合條件的資料、或是有多筆資料符合條件，都會產生 exception）  
  filter：返回符合條件的陣列。如果找不到任何資料則會返回空陣列。

## 2.4 girl Django - show DB at templat  
* **home page view**  
trips/views.py  
```python
from .models import Post
def home(request):
    post_list =  Post.objects.all()
    return render(request, 'home.html', {
        'post_list': post_list,
    })
```

* **home page url point to root**  
demo_site/urls.py  
```python
from trips.views import hello_world,home
urlpatterns = [
	....
    path('', home),
]
```

* **home template**  
templates/home.html
```html
{{ post_list }}
```

* **home template(show more tetail)**  
```html
{% for post in post_list %}
	<div>
	{{ post.title }}
	{{ post.content }}
	{{ post.photo }}
	{{ post.created_at }}
	</div>
{% endfor %}
```

* **home template(show photo)**  
```html
{% for post in post_list %}
	<div>
	{{ post.title }}
	{{ post.content }}
	{{ post.created_at }}
	{% if post.photo %}
		<div class="thumbnail">
    		<img src="{{ post.photo }}" alt="">
		</div>
	{% else %}
		<div class="thumbnail thumbnail-default"></div>
	{% endif %}
	</div>
{% endfor %}
```

* **home template(show time format)**  
```html
{% for post in post_list %}
	<div>
	{{ post.title }}
	{{ post.content }}
	{{ post.created_at|date:"Y/m/d H:i:s" }}
	{% if post.photo %}
		<div class="thumbnail">
    		<img src="{{ post.photo }}" alt="">
		</div>
	{% else %}
		<div class="thumbnail thumbnail-default"></div>
	{% endif %}
	</div>
{% endfor %}
```

* **home template(complete ccs/html)** 
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>A Django Girl's Adventure</title>
    <link href="//fonts.googleapis.com/css?family=Lemon" rel="stylesheet" type="text/css">
    <link href="//maxcdn.bootstrapcdn.com/font-awesome/4.2.0/css/font-awesome.min.css" rel="stylesheet" type="text/css">
    <link href="//djangogirlstaipei.github.io/assets/css/style.css" rel="stylesheet" type="text/css">
</head>
<body>
    <div class="header">
        <h1 class="site-title text-center">
            <a href="/">A Django Girl’s Adventure</a>
        </h1>
    </div>
    <div class="container">
        {% for post in post_list %}
        <div class="post-wrapper">
            <div class="post">
                <div class="post-heading">
                    <h2 class="title">
                        <a href="#">{{ post.title }}</a>
                    </h2>
                    <div class="date">{{ post.created_at|date:"Y / m / d" }}</div>
                </div>
                {% if post.photo %}
                <div class="thumbnail">
                    <img src="{{ post.photo }}" alt="">
                </div>
                {% else %}
                <div class="thumbnail thumbnail-default"></div>
                {% endif %}
                <div class="post-content read-more-block">
                    {{ post.content }}
                </div>
                <div class="post-footer">
                    <a class="read-more" href="#">
                        Read More <i class="fa fa-arrow-right"></i>
                    </a>
                </div>
            </div>
        </div>
        {% endfor %}
    </div>
</body>
</html>
```

* **template tags**  
```html
# --- for --- 
{% for <element> in <list> %}
    ...
{% endfor %}
# --- if else --- 
{% if var1 %}
    {{ var1 }}
{% elif var2 %}
    {{ var2 }}
{% else %}
    {{ var3 }}
{% endif %}
# --- url  ---
{% url '<url_name>' %} : 根據在 urls.py 中設定的「name」值，找到對應的 URL
{% url '<url_name>' arg1=<var1> arg2=<var2> ...%} : 傳入參數
```

* **template filter**  
```
{{<variable_name>|<filter_name>:<filter_arguments>}}
# date example
{{ value|date:"D d M Y" }}
# ---
<variable_name> -- 變數名稱  
<filter_name> -- filter 名稱，例如 add、cut 等等  
<filter_arguments> -- 要傳入 filter 的參數  
```

## 2.5 girl Django - dynamic url  
* **single article page view**  
trips/views.py  
```python
def post_detail(request,pk):
    post =  Post.objects.get(pk=pk)
    return render(request, 'post.html', {'post': post})
```

* **single article page url point to root**  
demo_site/urls.py
```python
from django.urls import path, re_path
from trips.views import hello_world, home, post_detail
urlpatterns = [
	....
    re_path(r'^post/(?P<pk>\d+)/$', post_detail),
]
```

* **single article page template**  
templates/post.html
```html
{{ post }}
```

* **single article page template(complete ccs/html)**  
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>{{ post.title }} | A Django Girl’s Adventure</title>
    <link href="//fonts.googleapis.com/css?family=Lemon" rel="stylesheet" type="text/css">
    <link href="//maxcdn.bootstrapcdn.com/font-awesome/4.2.0/css/font-awesome.min.css" rel="stylesheet" type="text/css">
    <link href="//djangogirlstaipei.github.io/assets/css/style.css" rel="stylesheet" type="text/css">
</head>
<body>
    <div class="header">
        <h1 class="site-title text-center">
            <a href="/">A Django Girl’s Adventure</a>
        </h1>
    </div>
    <div class="container post post-detail">
        <div class="post-heading">
            <h1 class="title">{{ post.title }}</h1>
            <div class="date">{{ post.created_at|date:'Y / m / d' }}</div>
        </div>
        <div class="location">
            <i class="fa fa-map-marker"></i>
            <span id="location-content">{{ post.location }}</span>
        </div>
        <div id="map-canvas" class="map"></div>
        <div class="post-content">
            {{ post.content }}
        </div>
        <hr class="fancy-line">
        <img class="photo" src="{{ post.photo }}" alt="Cover photo for {{ post.title }}">
    </div>
    <script src="//maps.googleapis.com/maps/api/js?v=3.exp&libraries=places&sensor=false"></script>
    <script src="//djangogirlstaipei.github.io/assets/js/map.js"></script>
</body>
</html>
```

* **使用 Regex 提取部份 URL 為參數**  
Django 的 URL 是一個 regular expression (regex)  
```
(?P<pk>\d+)
```
	* \d 代表一個阿拉伯數字。
	* '+' 代表「一個以上」。
	* 所以 \d+ 代表一個以上的阿拉伯數字，例如「0」、「99」、「12345」。可是像「8a」就不符合，因為「a」不是數字。  
	(?P<pk>) 代表「把這一串東西抓出來，命名為 pk。
	* <b class="Red">用 pk 有一些問題,因pk為 DB generate record index,若曾經刪除,pk值為不連續,有些不存在</b>  

* **put url to home page**  
	* add url name for post_deatil  
	demo_site/urls.py
	```python
	urlpatterns = [
		....
	    re_path(r'^post/(?P<pk>\d+)/$', post_detail, name='post_detail'),
	]
	```

	* add url to home page(title and read-more)  
	templates/home.html
	```html
    <div class="post-heading">
        <h2 class="title">
            <a href="{% url 'post_detail' pk=post.pk %}">{{ post.title }}</a>
        </h2>
        <div class="date">{{ post.created_at|date:"Y / m / d" }}</div>
    </div>
    ....
    <div class="post-footer">
        <a class="read-more" href="{% url 'post_detail' pk=post.pk %}">
            Read More <i class="fa fa-arrow-right"></i>
        </a>
    </div>
	```

## 3. Django - projrct/app create
* **create project**  
django-admin startproject mysite  
cd mysite  
python manage.py runserver  

* **add app**  
python manage.py startapp polls  

* **app's view and urls.py**  
  * polls/views.py  
  ```python
  from django.http import HttpResponse
  # --
  def index(request):
    return HttpResponse("Hello, You are at the polls index")
  ```

  * add polls/urls.py 
  ```python
  from django.urls import path
  # --
  from . import views
  urlpatterns = [
    path('', views.index, name='index')
  ]
  ```

* **add app urls to project's url**  
> mysite/urls.py  
  The include() function allows referencing other URLconfs.  
```python
from django.contrib import admin
from django.urls import path, include
# --
urlpatterns = [
    path('admin/', admin.site.urls),
    path('polls/', include('polls.urls')),
]
```

## 3.1 Django - Database 
> SQLite is included in Python

* **project setting**  
mysite/settings.py  
```python
# --- default Database ----
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}
# --- default Time Zone ----
# TIME_ZONE = 'UTC'
TIME_ZONE = 'Asia/Taipei'
# --- installed apps ----
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]
```
> python manage.py migrate - update for databse change  

* **models-database setting**  
    * set modules  
    polls/models.py  
    ```python
    from django.db import models  
    # --
    class Question(models.Model):
      question_text = models.CharField(max_length=200)
      pub_date = models.DateTimeField('data published')
    # --
    class Choice(models.Model):
      question = models.ForeignKey(Question, on_delete=models.CASCADE)
      choice_text = models.CharField(max_length=200)
      votes = models.IntegerField(default=0)
    ```
    > pub_date = models.DateTimeField('data published') - 'data published': human-readable name  

    * add app  
    mysite/settings.py  
    ```python
    INSTALLED_APPS = [
        'polls.apps.PollsConfig',
        ....
    ]
    ```
    > The PollsConfig in pools/apps.py  

    * app model makemigrations  
    python manage.py makemigrations polls  
    ```python
    # --> response 
    Migrations for 'polls':
      polls\migrations\0001_ini
        - Create model Question
        - Create model Choice
    ```

    * polls sql migrate  
    python manage.py sqlmigrate polls 0001  
    ```python
    # --> respons
    # BEGIN;
    # --
    # -- Create model Question
    # --
    # CREATE TABLE "polls_question" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT,
    # "question_text" varchar(200) NOT NULL, "pub_date" datetime NOT NULL);
    # --
    # -- Create model Choice
    # --
    # CREATE TABLE "polls_choice" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT, "c
    # hoice_text" varchar(200) NOT NULL, "votes" integer NOT NULL, "question_id" integ
    # er NOT NULL REFERENCES "polls_question" ("id") DEFERRABLE INITIALLY DEFERRED);
    # CREATE INDEX "polls_choice_question_id_c5b4b260" ON "polls_choice" ("question_id
    # ");
    # COMMIT;
    ```

    * check any issue ?(only check)  
    python manage.py check  
    ```
    # --> response
    System check identified no issues (0 silenced).
    ```

    * migrate project  
    python manage.py migrate
    ```
    # --> response
    Operations to perform:
      Apply all migrations: admin, auth, contenttypes, polls, sessions
    Running migrations:
      Applying polls.0001_initial... OK
    ```

    * python django shell  
    python manage.py shell  
    ```
    >>> from polls.models import Question, Choice
    >>> Question.objects.all()
    <QuerySet []>

    >>> from django.utils import timezone
    // insert record
    >>> q = Question(question_text="What's new?", pub_date=timezone.now())
    >>> q.save()
    >>> q.id
    1

    >>> q.question_text
    "What's new?"
    >>> q.pub_date
    datetime.datetime(2019, 9, 29, 12, 19, 32, 453076, tzinfo=<UTC>)
    >>> q.question_text = "What's up?"
    >>> q.save()
    // show all for Question 
    >>> Question.objects.all()
    <QuerySet [<Question: Question object (1)>]>
    ```

    * python DB return string function + addtion function   
    polls/models.py    
    ```python
    import datetime
    from django.utils import timezone
    ....
    class Question(models.Model):
        ....
        def __str__(self):
            return self.question_text
        def was_published_recently(self):
            return self.pub_date >= timezone.now() - datetime.timedelta(days=1)
    class Choice(models.Model):
        ....
        def __str__(self):
            return self.choice_text
    ```

    * migrate  
    python manage.py migrate  

    * DB access  
    python manage.py shell  
    ```
    >>> from polls.models import Question, Choice
    // return str 
    >>> Question.objects.all()
    <QuerySet [<Question: What's up?>]>

    // filter by id
    >>> Question.objects.filter(id=1)
     <QuerySet [<Question: What's up?>]>
    // filter by start stringid
    >>> Question.objects.filter(question_text__startswith='What')
    <QuerySet [<Question: What's up?>]>

    >>> from django.utils import timezone
    >>> current_year = timezone.now().year
    // get for year condition  
    >>> Question.objects.get(pub_date__year=current_year)
    <Question: What's up?>
    >>> Question.objects.get(id=1)
    <Question: What's up?>

    // get not exist is 
    >>> Question.objects.get(id=2)
    # ---------------------------------------------------------------------------
    DoesNotExist                              Traceback (most recent call last)
    ....
    DoesNotExist: Question matching query does not exist.

    // run addition function - was_published_recently 
    // pk meaning same as id 
    >>> q = Question.objects.get(pk=1)
    >>> q.was_published_recently()
    True

    >>> q = Question.objects.get(id=1)
    // display any choice from related object  
    >>> q.choice_set.all()

    // create choices 
    >>> q.choice_set.create(choice_text='Not much' ,votes=0)
    <Choice: Not much>
    >>> q.choice_set.create(choice_text='The sky' ,votes=0)
    <Choice: The sky>
    >>> c = q.choice_set.create(choice_text='Just hacking again' ,votes=0)
    >>> c.question
    <Question: What's up?>

    // display choice and counter - I input wrong so have more thern 3 record 
    >>> q.choice_set.all()
    <QuerySet [<Choice: Not much>, <Choice: Not much>, <Choice: Not much>, <
        Choice: The sky>, <Choice: Just hacking again>]>
    >>> q.choice_set.count()
    5

    // display year condition for choice 
    >>> Choice.objects.filter(question__pub_date__year=current_year)
    <QuerySet [<Choice: Not much>, <Choice: Not much>, <Choice: Not much>,
    <Choice: The sky>, <Choice: Just hacking again>]>

    // filter by condition then delete 
    >>> c = q.choice_set.filter(choice_text__startswith='Just hacking')
    >>> c.delete()
    (1, {'polls.Choice': 1})
    >>> Choice.objects.filter(question__pub_date__year=current_year)
    <QuerySet [<Choice: Not much>, <Choice: Not much>, <Choice: Not much>,
    <Choice: The sky>]>
    ```

    * create super user  
    python manage.py createsuperuser  
    web admin interface : http://127.0.0.1:8000/admin/

    * register poll model to admin  
    polls/admin.py  
    ```python 
    from django.contrib import admin
    from .models import Question, Choice
    admin.site.register(Question)
    admin.site.register(Choice)
    ```

## 3.2 Django - add more view  
* **add view**  
polls/views.py  
```python
from django.http import HttpResponse
def index(request):
    return HttpResponse("Hello, You are at the polls index")
def detail(request, question_id):
    return HttpResponse("you're looking at question %s." % question_id)
def results(request, question_id):
    response = "You're looking at the results of question %s."
    return HttpResponse(response % question_id)
def vote(request, question_id):
    return HttpResponse("you're voting on question %s." % question_id)
```

* **add app url**  
polls/urls.py  
```python
from django.urls import path
from . import views
urlpatterns = [
    # ex : /pools/
    path('', views.index, name='index'),
    # ex : /pools/5/
    path('<int:question_id>/', views.detail, name='detail'),
    # ex : /pools/5/results/
    path('<int:question_id>/results/', views.results, name='results'),
    # ex : /pools/5/vote/
    path('<int:question_id>/vote/', views.vote, name='vote'),
]
```

* **try web access**  
http://127.0.0.1:8000/polls/50/  
http://127.0.0.1:8000/polls/50/results/  
http://127.0.0.1:8000/polls/50/vote/  
> It response success.  
  It seem caa : detail(request=<HttpRequest object>, question_id=34)  

* **modify index view - show DB**  
polls/views.py  
```python
from .models import Question
def index(request):
    # return HttpResponse("Hello, You are at the polls index")
    latest_question_list = Question.objects.order_by('-pub_date')[:5]
    output = ', '.join([q.question_text for q in latest_question_list])
    return HttpResponse(output)
```

* **add template - for HTML template**  
create templates directory in polls  
polls/templates/polls/index.html  
```python
{% if latest_question_list %}
    <ul>
        {% for question in latest_question_list %}
        <li> 
            <a href="/polls/{{question.id}}/">{{question.question_text}}/</a>
        </li>
        {% endfor %}
    </ul>
{% else %}
    <p>No polls are available.</p>
{% endif %}
```

* **default TEMPLATES APP_DIRS set true**  
mysite/settings.py  
```python
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [],
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

* **change view for template**  
polls/views.py  
```python
from django.template import loader
def index(request):
    latest_question_list = Question.objects.order_by('-pub_date')[:5]
    template = loader.get_template('polls/index.html')
    content = {
        'latest_question_list' : latest_question_list,
    }
    return HttpResponse(template.render(content, request))
```

* **change view to shortcut: render()**  
polls/views.py  
```python
from django.shortcuts import render
def index(request):
    latest_question_list = Question.objects.order_by('-pub_date')[:5]
    content = {
        'latest_question_list' : latest_question_list,
    }
    return render(request, 'polls/index.html', content)
```

* **Raising a 404 error - detail view**  
polls/views.py  
```python
from django.http import Http404
from django.shortcuts import render
def detail(request, question_id):
    try:
        question = Question.objects.get(id=question_id)
    except Question.DoesNotExist:
        raise Http404("Question does not exist.")
    return render(request, 'polls/detail.html', {'question': question})
```
polls/templates/polls/detail.html  
```html
{{ question }}
```

* **shortcut get_object_or_404()**  
polls/views.py  
```python
from django.shortcuts import get_object_or_404
def detail(request, question_id):
    question = get_object_or_404(Question, id=question_id)
    return render(request, 'polls/detail.html', {'question': question})
```

* **Use the template system**  
polls/templates/polls/detail.html  
```html
<h1>{{ question.question_text }}</h1>
<ul>
    {% for choice in question.choice_set.all %}
        <li>{{ choice.choice_text }}</li>
    {% endfor %}
</ul>
```
> variable :  {{ question.question_text }}  
  method : {% for.. %} {% endfor %}  
  DB function :  question.choice_set.all  

* **Removing hardcoded URLs in templates**  
polls/templates/polls/index.html  
```html
<a href="/polls/{{question.id}}/">{{question.question_text}}/</a>
to 
<a href="{% url 'detail' question.id %}">{{question.question_text}}/</a>
```
template url configurations  
```
{% url '<url_name>' arg1=<var1> arg2=<var2> ...%}  
<url_name> map to urls.py name's url :  
  path('<int:question_id>/', views.detail, name='detail'),
```

* **Namespacing URL names**  
consider mutiple app have same name  
polls/urls.py   
```python
# add app's name for url
app_name = 'pools'
urlpatterns = [
    ....
]
```
polls/templates/polls/index.html  
```html
<a href="{% url 'detail' question.id %}">{{question.question_text}}/</a>
to 
<a href="{% url 'pools:detail' question.id %}">{{question.question_text}}/</a>
```

## 3.3 Django - add a simple form  
* **deatil.html**  
polls/templates/polls/detail.html  
```html
<h1>{{ question.question_text }}</h1>
{% if error_message %}
	<p><strong>{{ error_message }}</strong></p>
{% endif %}
<!-- -->
<form action="{% url 'polls:vote' question.id %}" method="post">
	{% csrf_token %}
	<!-- -->
	{% for choice in question.choice_set.all %}
		<input type="radio" name="choice" id="choice{{ forloop.counter }}" value="{{ choice.id }}">
		<label for="choice{{ forloop.counter }}">{{ choice.choice_text }}</label>	
		<br>
	{% endfor %}
	<input type="submit" value="Vote">
</form>
```
> form action: point tu url  
  method="post" 資料傳遞時，網址並不會改變  
  method="get" 網址會帶有 HTML Form 表單的參數與資料  
  {{ forloop.counter }}: for index  
  {% csrf_token %}: Django 防止偽造 command 送至 server  

* **view**  
polls/views.py  
```python
from django.http import HttpResponse, HttpResponseRedirect
from django.urls import reverse
from .models import Question, Choice
def vote(request, question_id):
    question = get_object_or_404(Question, pk=question_id)
    try :
        selected_choice = question.choice_set.get(pk=request.POST['choice'])
    except (KeyError, Choice.DoesNotExist):
        # redisplay the question voting form
        return render(request, 'polls/detail.html', {
            'question': question,
            'error_message': "You didn't select a choice.",
        })
    else :
        selected_choice.votes += 1
        selected_choice.save()
        return HttpResponseRedirect(reverse('polls:results', args=(question.id,)))
```
> request.POST['choice']: return choice id, GET 也有相同功能, 但 POST能防止資料直接顯露  
  (KeyError, Choice.DoesNotExist): triger by request.POST['choice'] not get data  
  HttpResponseRedirect: run it aftre POST data(Tt only take a single argument)  
  reverse(): avoid have hardcode URL  

* **do results view**  
polls/views.py  
```python
def results(request, question_id):
    question = get_object_or_404(Question, pk=question_id)
    return render(request, 'polls/results.html', {'question': question})
```

* **add results template**  
polls/templates/polls/results.html  
```html
<h1>{{ question.question_text }}</h1>
<!-- -->
<ul>
	{% for choice in question.choice_set.all %}
	<li>
		{{ choice.choice_text }} -- {{ choice.votes}} vote{{ choice.votes|pluralize }}
	</li>
	{% endfor %}
</ul>
<!-- -->
<a href="{% url 'polls:detail' question.id %}">Vote again?</a>
```


* **generic view**  
change url, view  
    * polls/urls.py  
	```python
	urlpatterns = [
		# ex : /polls/
		path('', views.IndexView.as_view(), name='index'),
		# ex : /polls/5/
		path('<int:pk>/', views.DetailView.as_view(), name='detail'),
		# ex : /polls/5/results/
		path('<int:pk>/results/', views.ResultsView.as_view(), name='results'),
		# ex : /polls/5/vote/
		path('<int:question_id>/vote/', views.vote, name='vote'),
	]
	```
	> some question_id change to pk  

    polls/views.py  
	```python
	from django.views import generic
	# --
	class IndexView(generic.ListView):
	    template_name = 'polls/index.html'
	    context_object_name = 'latest_question_list'
		# --
	    def get_queryset(self):
	        """　Return the last 5 published question"""
	        return Question.objects.order_by('-pub_date')[:5]
	# --
	class DetailView(generic.DetailView):
	    model = Question
	    template_name = 'polls/detail.html'
	# --
	class ResultsView(generic.DetailView):
	    model = Question
	    template_name = 'polls/results.html'
	# --
	def vote(request, question_id):
	    ...
	```
	> generic.ListView : display a list of objects  
	  generic.DetailView : display a detail page for a particular type of object.  
	  * The DetailView generic view expects the primary key value captured from the URL to be called "pk"  

* **know issue**  
	* race condition  
	 If two users of your website try to vote  


## 3.4 Django - automated tests  
* **test was_published_recently**  
python manage.py shell  
```python
>>> import datetime
>>> from django.utils import timezone
>>> from polls.models import Question
>>> # create a Question instance with pub_date 30 days in the future
>>> future_question = Question(pub_date=timezone.now() + datetime.timedelta(days=30))
>>> # was it published recently?
>>> future_question.was_published_recently()
True
```
> It's not correct.  

* **add test code**  
polls/tests.py  
```python
import datetime
# --
from django.test import TestCase
from django.utils import timezone
# --
from .models import Question
# --
class QuestionModelTests(TestCase):
	def test_was_publish_recently_with_future_question(self):
		"""
		was_published_recently() returns False for question whose pub_date is in the future 
		"""
		time = timezone.now() + datetime.timedelta(days=30)
		future_question = Question(pub_date=time)
		self.assertIs(future_question.was_published_recently(), False)
```

* **run test code**  
python manage.py test polls  
```
 Creating test database for alias 'default'...
 System check identified no issues (0 silenced).
 
 ----------------------------------------------------------------------
 Ran 1 test in 0.001s
 
 OK
 Destroying test database for alias 'default'...
 PS D:\work\python\django_work\mysite> python manage.py test polls
 Creating test database for alias 'default'...
 System check identified no issues (0 silenced).
 F
 ======================================================================
 FAIL: test_was_publish_recently_with_future_question (polls.tests.QuestionModelTests)
 ----------------------------------------------------------------------
 Traceback (most recent call last):
  File "D:\work\python\django_work\mysite\polls\tests.py", line 15, in test_was_publish_recently_with_future_question
    self.assertIs(future_question.was_published_recently(), False)
 AssertionError: True is not False

 ----------------------------------------------------------------------
 Ran 1 test in 0.001s

 FAILED (failures=1)
 Destroying test database for alias 'default'...
```
> It found a subclass of the django.test.TestCase class  
  It created a special database for the purpose of testing  
  Using the assertIs() method, it discovered that its was_published_recently() returns True, though we wanted it to return False  

* **fixing the bug**  
polls/models.py  
```python
	def was_published_recently(self):
		now = timezone.now()
		return now - datetime.timedelta(days=1) <= self.pub_date <= now
```

* **run test code**  
python manage.py test polls  
```
 PS D:\work\python\django_work\mysite> python manage.py test polls
 Creating test database for alias 'default'...
 System check identified no issues (0 silenced).
 
 ----------------------------------------------------------------------
 Ran 1 test in 0.001s
 
 OK
 Destroying test database for alias 'default'...
```

* **add more test code**  
polls/tests.py  
```python
	def test_was_published_recently_with_old_question(self):
		"""
		was_published_recently() returns False for questions whose pub_date
		is older than 1 day.
		"""
		time = timezone.now() - datetime.timedelta(days=1, seconds=1)
		old_question = Question(pub_date=time)
		self.assertIs(old_question.was_published_recently(), False)
	def test_was_published_recently_with_recent_question(self):
		"""
		was_published_recently() returns True for questions whose pub_date
		is within the last day.
		"""
		time = timezone.now() - datetime.timedelta(hours=23, minutes=59, seconds=59)
		recent_question = Question(pub_date=time)
		self.assertIs(recent_question.was_published_recently(), True)
```

* **run test code**  
python manage.py test polls  
```
 Creating test database for alias 'default'...
 System check identified no issues (0 silenced).
 ...
 ----------------------------------------------------------------------
 Ran 3 tests in 0.001s
 
 OK
 Destroying test database for alias 'default'...
```

* **test view(client)**  
	* test by shell  
	python manage.py shell  
	```
	// set test environment
	>>> from django.test.utils import setup_test_environment
	>>> setup_test_environment()
	// import tel client class
	>>> from django.test import Client
	>>> # create an instance of the client for our use
	>>> client = Client()
	// get a response from '/'
	>>> response = client.get('/')
	Not Found: /
	>>> response.status_code
	404
     
	// reverse(): avoid have hardcode URL  
	>>> from django.urls import reverse
	>>> response = client.get( reverse('polls:index'))
	>>> response.status_code
	200
	>>> response.content
	b'\n\t<ul>\n\t\t\n\t\t<li> \n\t\t\t<a href="/polls/3/">What&#39;s 10-2?/</a>\n\t\t</li>\n\t\t\n\t\t<li> \n\t\t\t<a href="/polls/2/">What&#39;s wrong./</a>\n\t\t</li>\n\t\t\n\t\t<li> \n\t\t\t<a href="/polls/1/">What&#39;s up?/</a>\n\t\t</li>\n\t\t\n\t</ul>\n\n\n'
	// get 'latest_question_list' context  
	>>> response.context['latest_question_list']
	<QuerySet [<Question: What's 10-2?>, <Question: What's wrong.>, <Question: What's up?>]>
	```
	* fix index view  
	fix index page retuen future date data  
	polls/views.py
	```python
	from django.utils import timezone
	class IndexView(generic.ListView):
	    template_name = 'polls/index.html'
	    context_object_name = 'latest_question_list'
	    def get_queryset(self):
	        """　Return the last 5 published question"""
	        return Question.objects.filter( pub_date__lte=timezone.now()).order_by('-pub_date')[:5]
	```

	* add index page test to test.py  
	polls/tests.py
	```python
	from django.urls import reverse
	def create_question(question_text, days):
	    """
	    Create a question with the given `question_text` and published the
	    given number of `days` offset to now (negative for questions published
	    in the past, positive for questions that have yet to be published).
	    """
	    time = timezone.now() + datetime.timedelta(days=days)
	    return Question.objects.create(question_text=question_text, pub_date=time)
	# --
	class QuestionIndexViewTests(TestCase):
	    def test_no_questions(self):
	        """
	        If no questions exist, an appropriate message is displayed.
	        """
	        response = self.client.get(reverse('polls:index'))
	        self.assertEqual(response.status_code, 200)
	        self.assertContains(response, "No polls are available.")
	        self.assertQuerysetEqual(response.context['latest_question_list'], [])
	# --
	    def test_past_question(self):
	        """
	        Questions with a pub_date in the past are displayed on the
	        index page.
	        """
	        create_question(question_text="Past question.", days=-30)
	        response = self.client.get(reverse('polls:index'))
	        self.assertQuerysetEqual(
	            response.context['latest_question_list'],
	            ['<Question: Past question.>']
	        )
	# --			
	    def test_future_question(self):
	        """
	        Questions with a pub_date in the future aren't displayed on
	        the index page.
	        """
	        create_question(question_text="Future question.", days=30)
	        response = self.client.get(reverse('polls:index'))
	        self.assertContains(response, "No polls are available.")
	        self.assertQuerysetEqual(response.context['latest_question_list'], [])
	# --
	    def test_future_question_and_past_question(self):
	        """
	        Even if both past and future questions exist, only past questions
	        are displayed.
	        """
	        create_question(question_text="Past question.", days=-30)
	        create_question(question_text="Future question.", days=30)
	        response = self.client.get(reverse('polls:index'))
	        self.assertQuerysetEqual(
	            response.context['latest_question_list'],
	            ['<Question: Past question.>']
	        )
	# --
	    def test_two_past_questions(self):
	        """
	        The questions index page may display multiple questions.
	        """
	        create_question(question_text="Past question 1.", days=-30)
	        create_question(question_text="Past question 2.", days=-5)
	        response = self.client.get(reverse('polls:index'))
	        self.assertQuerysetEqual(
	            response.context['latest_question_list'],
	            ['<Question: Past question 2.>', '<Question: Past question 1.>']
	        )
	```
	> create_question() : for create question record function  
	  django.test.TestCase support some test assertion methods, assertEqual(). assertQuerysetEqual()..   
	  The database is reset for each test method  

	* run test code  
	python manage.py test polls

	* fix detail view  
	fix detail page retuen future date data  
	polls/views.py  
	```python
	class DetailView(generic.DetailView):
		....
	    def get_queryset(self):
	        """
	        Excludes any questions that aren't published yet.
	        """
	        return Question.objects.filter( pub_date__lte=timezone.now())
	```

	* add detail page test to test.py  
	polls/tests.py  
	```python
	class QuestionDetailViewTests(TestCase):
	    def test_future_question(self):
	        """
	        The detail view of a question with a pub_date in the future
	        returns a 404 not found.
	        """
	        future_question = create_question(question_text='Future question.', days=5)
	        url = reverse('polls:detail', args=(future_question.id,))
	        response = self.client.get(url)
	        self.assertEqual(response.status_code, 404)
	    def test_past_question(self):
	        """
	        The detail view of a question with a pub_date in the past
	        displays the question's text.
	        """
	        past_question = create_question(question_text='Past Question.', days=-5)
	        url = reverse('polls:detail', args=(past_question.id,))
	        response = self.client.get(url)
	        self.assertContains(response, past_question.question_text)
	```


## 3.5 Django - add static files  
* **put static file** 
	* create directory for static files  
	polls/static  

	* add css 
	polls/static/polls/style.css
	```html
	li a {
		color: orange
	}
	``` 

	* modify template  
	polls/templates/polls/index.html  
	```html
	{% load static %}
	<link rel="stylesheet" type="text/css" href="{% static 'polls/style.css' %}">
	```
	> The index page's show orange for link  

	* add background image  
	polls/static/polls/images/background.jpg  

	* add image to background  
	polls/static/polls/style.css
	```html
	body {
		background: url("images/background.jpg") no-repeat;
	}
	``` 

## 3.6 Django - customize admin form  
* **change Question input** 
	* add Question admin page function  
	polls/admin.py  
	```python
	class QuestionAdmin(admin.ModelAdmin):
		fields = ['pub_date', 'question_text']
	# admin.site.register(Question)
	admin.site.register(Question, QuestionAdmin)
	```
	* add fieled title  
	polls/admin.py  
	```python
	class QuestionAdmin(admin.ModelAdmin):
		fieldsets = [
			(None, { "fields": ['question_text']}),
			('Date information', { "fields": ['pub_date']}),
		]
	```
	* admin Question add Choice - link by ForeignKey  
	polls/admin.py  
	```python
	class ChoiceInLine(admin.StackedInline):
		model =  Choice
		extra = 3
	class QuestionAdmin(admin.ModelAdmin):
		fieldsets = [
			(None, { "fields": ['question_text']}),
			('Date information', { "fields": ['pub_date']}),
		]
		inlines = [ChoiceInLine]
	```
	> extra : reserve input items 

	* Choice change to tabular - save space  
	polls/admin.py  
	```python
	class ChoiceInLine(admin.TabularInline):
		model =  Choice
		extra = 3
	```

	* add Question show field and models function  
	polls/admin.py  
	```python
	class QuestionAdmin(admin.ModelAdmin):
		list_display = ('question_text', 'pub_date', 'was_published_recently')
		....
	```
	> default just show str() of each object  

	* change models function display attributes   
	polls/models.py  
	```python
	def was_published_recently(self):
		now = timezone.now()
		return now - datetime.timedelta(days=1) <= self.pub_date <= now
	was_published_recently.admin_order_field = 'pub_date'
	was_published_recently.short_description = 'Published recent?'
	was_published_recently.boolean = True
	```
	> boolean : change to show icon  

	* add filter/search field  
	polls/admin.py  
	```python
	class QuestionAdmin(admin.ModelAdmin):
		list_filter = ['pub_date']
		search_fields = ['question_text']
	```
* **Customizing your project’s admin templates** 
	* add template directory  
	mysite/settings.py  
	```python
	TEMPLATES = [
	    {
	        'BACKEND': 'django.template.backends.django.DjangoTemplates',
	        # 'DIRS': [],
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

	* check Django source files position  
	python -c "import django; print(django.__path__)"  

	* copy defult teplate then modify  
	creste directory : templates/admin  
	copy template file from : django/contrib/admin/templates/base_site.html  
	modify as bellow  
	```html
	<h1 id="site-name"><a href="{% url 'admin:index' %}">{{ site_header|default:_('Head Django administration') }}</a></h1>
	to 
	<h1 id="site-name"><a href="{% url 'admin:index' %}">Polls Administration</a></h1>
	```

	* if need modify other template file  
	index.html...  

## 3.7 Django - Packaging your app  
* **Packaging your app**
    * move polls app  
    create directory django_polls  
    copy /polls to django_polls  
    * add some file for package  
    add file README.rst - example  
    ```python 
    # =====
    # Polls
    # =====
    # Polls is a simple Django app to conduct Web-based polls. For each
    # question, visitors can choose between a fixed number of answers.
    # Detailed documentation is in the "docs" directory.
    # Quick start
    # 1. Add "polls" to your INSTALLED_APPS setting like this::
    #     INSTALLED_APPS = [
    #         ...
    #         'polls',
    #     ]
    # 2. Include the polls URLconf in your project urls.py like this::
    #     path('polls/', include('polls.urls')),
    # 3. Run `python manage.py migrate` to create the polls models.
    # 4. Start the development server and visit http://127.0.0.1:8000/admin/
    #    to create a poll (you'll need the Admin app enabled).
    # 5. Visit http://127.0.0.1:8000/polls/ to participate in the poll.
    ```
    add file LICENSE  
    add file setup.py - example  
    ```python
    import os
    from setuptools import find_packages, setup
    with open(os.path.join(os.path.dirname(__file__), 'README.rst')) as readme:
        README = readme.read()
    # allow setup.py to be run from any path
    os.chdir(os.path.normpath(os.path.join(os.path.abspath(__file__), os.pardir)))
    setup(
        name='django-polls',
        version='0.1',
        packages=find_packages(),
        include_package_data=True,
        license='BSD License',  # example license
        description='A simple Django app to conduct Web-based polls.',
        long_description=README,
        url='https://www.example.com/',
        author='Your Name',
        author_email='yourname@example.com',
        classifiers=[
            'Environment :: Web Environment',
            'Framework :: Django',
            'Framework :: Django :: X.Y',  # replace "X.Y" as appropriate
            'Intended Audience :: Developers',
            'License :: OSI Approved :: BSD License',  # example license
            'Operating System :: OS Independent',
            'Programming Language :: Python',
            'Programming Language :: Python :: 3.5',
            'Programming Language :: Python :: 3.6',
            'Topic :: Internet :: WWW/HTTP',
            'Topic :: Internet :: WWW/HTTP :: Dynamic Content',
        ],
    )
    ```
    add file MANIFEST.in - for include additional files  
    ```
    include LICENSE
    include README.rst
    recursive-include polls/static *
    recursive-include polls/templates *
    ```

    add docs directory - if need  
    ```
    recursive-include docs *
    ```

    * building to package  
    python setup.py sdist  
    generate to dist/django-polls-0.1.tar.gz  

* **using polls app**
    * install polls package(windows)  
    pip install --user "django_polls/dist/django-polls-0.1.tar.gz"  
    * uninstall polls package - if need  
    pip uninstall django-polls  

    * create project  
    django-admin startproject mypoll  
    cd mypoll  

    * add polls app  
    mypoll/settings.py  
    ```python
    INSTALLED_APPS = [
        ....
        'polls',
    ]
    ```

    * add polls urls  
    mypoll/urls.py  
    ```python
    from django.urls import path, include
    urlpatterns = [
        ....
        path('polls/', include('polls.urls')),
    ]
    ```

    * run migrate  
    python manage.py migrate  

    * add super user  
    python manage.py createsuperuser  

    * start server  
    python manage.py runserver  

    * run web admin add record  
    http://127.0.0.1:8000/admin/  

    * run polls  
    http://127.0.0.1:8000/polls/  

## other.  
* **some setting**  
	* settings.py  
	```
	# 時區 - 依需要修改
	TIME_ZONE = 'Asia/Taipei'
	# 這個密匙值，是Django網站安全策略的一部分。如果在開發環境中，沒有保護好這個密匙，把代碼投入生產環境時，最好用不同的密匙代替。（可能從環境變量或文件中讀取）。
	SECRET_KEY = '=b(vf2xry9k65(5k757_miu-ug9s66tq=*^f78-!=7_u$sym1%'
	# debug - 這個會在debug日誌裡輸出錯誤信息，而不是輸入H​​TTP的返回碼。在生產環境中，它應設置為false，因為輸出的錯誤信息，會幫助想要攻擊網站的人。
	DEBUG = True
	# database setting 
	DATABASES = {
	    'default': {
	        'ENGINE': 'django.db.backends.sqlite3',
	        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
	    }
	}
	```
	***

* **command**  
	* python manage.py makemigrations  
	```
	add margin  
	```
	
	* python manage.py migrate  
	```
	update margin  
	每次模型改變，都需要運行以上命令，來影響需要存放的數據結構（包括添加和刪除整個模型和單個字段）  
	```

* **some site for python** 
	* [The Python Package Index(PyPI)](https://pypi.org) : some python library  
	* [Virtualenv](https://virtualenv.pypa.io/en/latest/#) : A tool to create isolated Python environments  

* **some error**  
	* No module named 'sqlparse'  
	```
	# ModuleNotFoundError: No module named 'sqlparse'
	conda install sqlparse
	```

	* add 'testserver' to ALLOWED_HOSTS.  
	Invalid HTTP_HOST header: 'testserver'. You may need to add 'testserver' to ALLOWED_HOSTS.  
	mysite/settings.py  
	```python
	ALLOWED_HOSTS = ['127.0.0.1','testserver']
	# Application definition
	INSTALLED_APPS = [
	    'polls.apps.PollsConfig',
	    'django.contrib.admin',
	    'django.contrib.auth',
	    'django.contrib.contenttypes',
	    'django.contrib.sessions',
	    'django.contrib.messages',
	    'django.contrib.staticfiles',
	]
	```

django-xx : Django's app


# format

## HTML
```python
from bs4 import BeautifulSoup
html_str = """
<html>
  <head>
    <title>The Avengers</title>
  </head>
  <body>
    <div id="header">
      <h1>Movies</h1>
    </div>
    <div id="movie-titles">
      <ul>
        <li id="movie-0" class="movies">
          <a href="https://www.imdb.com/title/tt0848228">The Avengers (2012)</a>
        </li>
        <li id="movie-1" class="movies">
          <a href="https://www.imdb.com/title/tt2395427">Avengers: Age of Ultron (2015)</a>
        </li>
        <li id="movie-2" class="movies">
          <a href="https://www.imdb.com/title/tt4154756">Avengers: Infinity War (2018)</a>
        </li>
        <li id="movie-3" class="movies">
          <a href="https://www.imdb.com/title/tt4154796">Avengers: Endgame (2019)</a>
        </li>
      </ul>
    </div>
  </body>
</html>
"""

soup = BeautifulSoup(html_str)
print(soup.find(id="movie-3").find("a").get("href"))
movie = soup.select("li#movie-3 a")
print(type(movie)) # list
print(movie[0]["href"])
```

## XPath-XML Path Language
單個正斜線 /：用來在樹狀結構中向下移動一層  
標記名稱：置放於正斜線之間用來定位資料  
中括號 []：用來指向同一個標記中的特定資料  
兩個正斜線 //：用來指向某個標記下的所有指定標記  
星號 * ：代表任意標記  
@ ：用來指定屬性，例如 id 、 class 或 href 等  
text() ：用來指定標記中所涵蓋的資料，即 <tag>...</tag> 中的 ...
```python
from lxml import etree

html_str = """
<html>
  <head>
    <title>The Avengers</title>
  </head>
  <body>
    <h1>Movies</h1>
    <p>The Avengers (2012)</p>
    <p>Avengers: Age of Ultron (2015)</p>
    <p>Avengers: Infinity War (2018)</p>
    <p>Avengers: Endgame (2019)</p>

    <div id="header">
      <h1>Movies</h1>
    </div>
    <div id="movie-titles">
    <a href="https://www.imdb.com/title/tt2395427">Avengers: Age of Ultron (2015)</a>
    <a href="https://www.imdb.com/title/tt4154756">Avengers: Infinity War (2018)</a>
    <a href="https://www.imdb.com/title/tt4154796">Avengers: Endgame (2019)</a>
    </div>
  </body>
</html>
"""
tree = etree.HTML(html_str)
print(tree)
print(tree.xpath("/html/body/p[4]/text()")[0])
print(type(tree)) # <class 'lxml.etree._Element'>
print(tree.xpath("/html/body/div[2]/a/@href")[1])
print(tree.xpath('//a/@href')[2])
```

## CSS Selector
#movie-3 > a {  
  font-size: 28px;  
}  
CSS Selector 指的便是大括號 {} 前所宣告的定位，簡單的 CSS Selector 可能由下列幾個元件所組成，與 XPath 有異曲同工之妙  
單個大於符號 >：用來在樹狀結構中向下移動一層（功能與 XPath 中的 / 相同）  
標記名稱：置放於大於符號之間用來定位資料  
:nth-of-type()：用來指向同一個標記中的特定資料（功能與 XPath 中的 [] 相同）  
空格：用來指向某個標記下的所有指定標記（功能與 XPath 中的 // 相同）  
星號 ＊：代表任意標記  
浮點 .：用來指定 class 屬性（功能與 XPath 中的 @ 功能相同）  
井字號 #：用來指定 id 屬性（功能與 XPath 中的 @ 功能相同）  
::text ：用來指定標記中所涵蓋的資料，即 <tag>...</tag> 中的 ...（功能與 XPath 中的 text() 相同）  
```python
from bs4 import BeautifulSoup

html_str = """
<html>
  <head>
    <title>The Avengers</title>
  </head>
  <body>
    <h1>Movies</h1>
    <p>The Avengers (2012)</p>
    <p>Avengers: Age of Ultron (2015)</p>
    <p>Avengers: Infinity War (2018)</p>
    <p>Avengers: Endgame (2019)</p>
  </body>
</html>
"""

soup = BeautifulSoup(html_str)
print(soup.select('html > body > p:nth-of-type(4)')[0].text)
print(soup.select('p:nth-of-type(4)')[0].text)
"""
```

# run

## 1. run jupyter notebook
Jupyter是一個非營利組織，旨在「為數十種程式語言的交互式計算開發開源軟體，開放標準和服務」。  
```
// run jupyter notebook (http://localhost:8888)
jupyter notebook

// force port number
jupyter notebook --port <port_number>

// only start server not run browser
jupyter notebook --no-browser

// run
Ctrl + Enter

// 支援 linlie 繪圖
%matplotlib inline 

// jupyter run python(在選擇目錄的時候可以按一下tab鍵，會出現提示)
%run -i 目錄/my_python_file.py
```

## 2. socket

* **import pckage**

```python
import socket
```  


* **function**

```python
socket.socket([family], [type] , [proto] )
```

# python 語法
## common
```python
// del - 將完成賦值的物件自環境中刪除
hello_msg = "Hello Python!"
print(hello_msg)
del hello_msg

// help() 函數查詢函數的說明文件
help(print)

# 計算指令運算時間
big_array = np.random.random(10000000) #在0到1間亂數值取10000000個
%timeit min(big_array)
```

## function

* **lambda**  
lambda 是種將運算式 (expression) 重複運用的方式，類似函數 (function) ，卻又不像函數需要額外命名函數的識別字 (identifier) ，因此又被稱為無名函數，基本上 lambda 運算式就是函數的簡化，因此某些需要函數的場合可以用 lambda 運算式代替

```python
a = lambda x: x ** 5 + 2
print(a)
print(a(2))
print(a(12))
```

* **print(python3)**  

```python
# print format
print('{0},{1}'.format('zhangk', 32))
print('{},{},{}'.format('zhangk','boy',32))
print('{name},{sex},{age}'.format(age=32,sex='male',name='zhangk'))

# 填充與對齊
# ：號後面帶填充的字符，只能是一個字符，不指定的話默認是用空格填充
# ^，<，>分別是居中，左對齊，右對齊，後面帶寬度
print('{:>8}'.format('zhang'))
print('{:0>8}'.format('zhang'))
print('{:a<8}'.format('zhang'))
print('{:p^10}'.format('zhang'))
	   zhang
	000zhang
	zhangaaa
	ppzhangppp

# 精度与类型f
print('{:.2f}'.format(31.31412))
	31.31

# 其他类型 :b、d、o、x分别是二进制、十进制、八进制、十六进制
print('{:b}'.format(15))
print('{:d}'.format(15))
print('{:o}'.format(15))
print('{:x}'.format(15))
	1111
	15
	17
	f

# 用逗号还能用来做金额的千位分隔符
print('{:,}'.format(123456789))
	123,456,789

#print 帶參數
print("the length of (%s) is %d" % ('runoob',len('runoob')))

# print 會自動在行末加上回車, 如果不需回車，只需在 print end=''
print("aa",end='')
print("bb")
print("cc","dd")
	aabb
	cc dd
```


* **os套件**

名稱			|說明
--------		|-----
system()		|	執行系統command
mkdir(E)		|	建立E目錄，如果E目錄已存在會發生錯誤
rmdir(E)		|	移除E目錄
remove(E)		|	移除E檔案，如果E是目錄就會出錯
getcwd()		|	取得目前所在路徑
rename(src, dst)|	將 src 改名為 dst

```python
import os
print(os.getcwd())
```

* **os.path有以下常用的函式**

名稱			|說明
--------		|-----
isfile(E) 		| E檔案是否存在
isdir(E) 		| E目錄是否存在
join(src, dst) 	| 拼接目錄，只有拼接，不會建立目錄
exists(E)		| 判斷文件或目錄是否存在
getsize(E) 		| 取得文件大小
abspath(E) 		| 獲得檔案的絕對路徑

```python
file = "day06-01.txt"
print("完整路徑名稱--->",os.path.abspath(file))  # 完整路徑名稱
print(file," 是否存在--->",os.path.exists(file)) # 是否存在
print(file," 檔案大小--->",os.path.getsize(file)) #取得檔案大小
```

* os.walk **取得目錄下所有檔案和目錄**

```python
import os
for root, dirs, files in os.walk("day06-dir"):
    for name in files:
        print("檔案--->",os.path.join(root, name))
    for name in dirs:
        print("目錄--->",os.path.join(root, name))
    print()
```

* **file**  
open(filename, mode)

文字	|說明
----	|----
r		|讀取
w		|寫入。檔案不存在則新增，檔案存在則寫入存在檔案
X		|寫入。只有當檔案不存在時才可寫入
a		|在檔案結尾處寫入
t		|文字
b		|二進位


```python
content = '''Python first   
測試中文
第三行
'''  # '''...'''  保留原本的格式
f = open('firstFile.txt','wt') # 寫入模式，檔案如果已經存在會被覆蓋
f.write(content)
f.close()
```

```python
#function 
def my_first_func():
    print('Call this function!')
my_first_func()
# 不定數目參數涵式
def sumNumber(*params):
    total = 0
    for param in params:
        total +=param
    return total
# 將function當作參數傳遞
def run_otherFunc(func):
    func(7,8)
run_otherFunc(GetArea)

# 常用內建函數
example1 = abs(-10)
print(example1)  #取得絕對值 輸出 10
example2 = chr(66)
print(example2)  #取得整數66的字元 輸出 B
example3 = divmod(33,6)
print(example3)  #取得33除以6的商數和餘數 輸出 (5, 3)
example4 = float(33)
print(example4)  #轉成浮點數 輸出 33.0
example5 = hex(33)
print(example5)  #轉成16進位 輸出 0x21
example6 = int(22.79)
print(example6)  #轉成整數(無條件捨去) 輸出 22
example7 = oct(33)
print(example7) #轉成八進位 輸出 0o41
example8 = ord("B")
print(example8) #取得Unicode編碼 輸出 66
example9 = pow(2,5)
print(example9) #取得2的5次方 輸出 32
example10 = round(22.79)
print(example10)  #轉成整數(四捨五入) 輸出 23
example11 = sum([11,22,33,44])
print(example11)  #取得list的總和 輸出 110


# 資料型態轉換
int() 轉換為整數
float() 轉換為浮點數
str() 轉換為字串

# 算術運算子
+, -, *, /, %, //(取得整除的商數), ** (次方, 7**2 = 49)

# 邏輯運算子
not, and, or  
&,|,^,~  

# type
print(type("xy"))
print(type(12))

# enumerate() 函數同時取得索引與數值
import numpy as np
arr = np.array([11, 12, 13, 14, 15])
for idx, val in enumerate(arr):
  print("位於索引值 {} 的數字是 {}".format(idx, val))

# print format
for i in range(nba_salary.shape[0]):
	print('{0:14}-{1:9}'.format(nba_salary.values[i][1], nba_salary.values[i][2]))
print("位於索引值 {} 的數字是 {}".format(idx, val))
# sep間隔 ,end結尾
print(100,200,300,sep="&",end="--")
# print format 
print("a=%d b=%d" % (10,20))
print("%s have %8.2f %s" % ("I", 99.0, "dollars"))

# input
name = input("Name:")

# string function
"HELLOW WORLD".lower() # 小寫
"hellow world".upper() # 大寫
"hellow world".title() # 第一個字母大寫
len("hellow world") # length
"Hello world".replace("l","!") # replace some char
# slipt string
"Hello my name is jiayi".split(" ")

# shuffle 隨機化代替列表中的項目
# random.shuffle(list)
row_indice = list(labeled_df.index)
random.Random(random_state).shuffle(row_indice)
shuffled = labeled_df.loc[row_indice, :]

#iolc 列切片及行切片
# 在 Python pandas 中可以使用 df.loc[m, n] 或 df.iloc[m, n] 兩個方法指定觀測值所在位置
# loc 基於行標籤和列標籤（x_label、y_label）進行索引
# iloc 基於行索引和列索引（index，columns） 都是從 0 開始

# reshape()  調整行列資料
X = np.arange(30).reshape((10, 3))

# dataframe.corr() 算出成對相關性(pairwise correlation)
```

## variable
```python
// type of variable
my_int = 87
my_float = 8.7
my_str = "Hello Python"
bool_true = True
bool_false = False
none_type = None
print(type(my_int))
print(type(my_float))
print(type(my_str))
print(type(bool_true))
print(type(bool_false))
print(type(none_type))

//
整數（int）
浮點數（float）-NaN(Not a Number, type=float)
文字（str）
布林（bool）
None（NoneType）
// test NaN
// inf : 是無限大,inf-inf或者-inf+inf是nan
import math
 a = float('nan')
print(math.isnan(x))

// 
+ 、 - 、 * 、 / ：加減乘除
** ：次方
% ：回傳餘數
// ：回傳商數
//
我們使用成雙的單引號 '' 或成對的雙引號 "" 來建立文字類型（str），多數的時候使用單引號或者雙引號不會有任何分別。
// 運用文字時常會使用到的技巧是以特定格式印出（print with format），以 .format() 方法作為實踐的管道，以 {} 作文字或者以 {:f} 做數值等不同類型的嵌入
shaq_height = 216
shaq_weight = 147
shaq_bmi = shaq_weight/(shaq_height/100)**2
print("俠客歐尼爾的 BMI 為 {}%".format(shaq_bmi))
print("俠客歐尼爾的 BMI 為 {:.2f}%".format(shaq_bmi))
// Python 在文字上運算的彈性較大一些，可以利用 + 進行文字的合併（concatenation），以及利用 * 進行複製。
first_name = "Shaquille"
last_name = "O'Neal"
print(first_name + " " + last_name)
print((first_name + " " + last_name + " ") * 3)
// 布林
bool 只有 True 與 False 這兩個值
// 比較
// == 、 != ：等於以及不等於
// > 、 >= 、 < 、 <= ：大於、大於等於、小於以及小於等於
// is 、 is not ：是否為相同的值與類型
// and 、 or ：交集與聯集
// not ：非
// in ：是否存在於
print(8 is 7) # 判斷 8 與 7 是否為同樣的類別或值
print(8 is not 7) # 判斷 8 與 7 是否為相異的類別或值
print(not(8 > 7)) # 反轉 8 是否大於 7 的判斷
print("H" in "Hello world") # 判斷 H 是否存在於 Hello world 之中
// 在 Python 中， True 跟數值 1 相等； False 跟數值 0 相等
print(True == 1)
print(False == 0)
print(1 + True)
print(1 + False)
// None 是所謂的無值，或者可以用 NA 值（Not Available）或 NaN 值（Not a Number）去體會它，None 是無回傳值函數中的預設輸出值、也是搜索特徵函數找不到情況下的預設輸出值
def hello_world():
  pass
print(hello_world()) # None
print(type(hello_world())) # <class 'NoneType'>
// 使用 isinstance(x, classinfo) 函數判斷純量類型，其中 x 輸入物件名稱、 classinfo 輸入類型名稱
# 判斷是否為整數
print(isinstance(87, int))
print(isinstance("87", int))
# 判斷是否為浮點數
print(isinstance(87.0, float))
print(isinstance(87, float))
# 判斷是否為文字
print(isinstance("True", str))
print(isinstance(True, str))
# 判斷是否為布林
print(isinstance(False, bool))
print(isinstance("False", bool))
# 判斷是否為 None
print(isinstance(None, type(None)))
print(isinstance("None", type(None)))
// 轉換純量類型的函數
// int()：轉換純量為整數類型
// float()：轉換純量為浮點數類型
// bool()：轉換純量為布林類型
// str()：轉換純量為文字類型
print(int(8.7))
print(int(True))
print(int(False))
print(int("87"))
print(float(87))
print(float(True))
print(float(False))
print(float("87"))
print(str(87))
print(str(87.0))
print(str(True))
print(str(False))
// input 
player_name = input("請輸入球員姓名：")
player_height = input("請輸入球員身高（cm）：")
player_weight = input("請輸入球員體重（kg）：")
player_height = float(player_height)
player_weight = float(player_weight)
player_bmi = player_weight/(player_height*0.01)**2
print("{}的身體質量指數為：{:.2f}".format(player_name, player_bmi))

// list、tuple、set、dict 
# list
h = list(range(0,10)) # range to list
h2 = h*2              # douple list
print(h2)
print(h2[2:7])
del h2[1:3]  # del
print(h2)
print(len(h2)) # 串列元素數目
print(min(h2)) # 串列元素最小值
print(max(h2)) # 串列元素最大值
print(h2.index(4)) # 元素在串列中第一次出現的index
print(h2.count(5)) # 元素在串列中出現的次數
# A.append(E)：在A串列中加入E元素
# A.extend(B)：在A串列中加入B串列的元素
# A.insert(B)：在A串列中加入B串列
# A.pop()：取出串列中最後一個元素，並且移除元素
# A.remove(E)：移除A串列中第一個出現E元素
# A.reverse()：反轉串列的順序
# A.sort()：將串列做排序

# Tuple(元組)：不能修改的List 用括號
# list和tuple互相轉換
ironman_tuple = ("中信兄弟", "統一獅", "lamigo", "富邦悍將")
ironman_list = ["brother","lion","monkey","Guardians"]
tuple_to_list = list(ironman_tuple)
list_to_tuple = tuple(ironman_list)

# Dict(字典)：key-map的形式
ironman_dict = {"team":"中信兄弟","year":"2017","ranking":2}
print(ironman_dict["team"])
# del A[key]：刪除元素 A[key]
# A.clear()：刪除A Dict所有元素
# del A：刪除A Dict
```

## collection
```python
// list 列表 - []
play_list = ["Robert Kao", "Leo lin", "Jerry Hsu"]
int_list = list(range(0,10))
print(int_list)
print(len(play_list))
print(play_list[1]) # left 2nd
print(play_list[-1]) # rigit 1st
# 切割
print(int_list[1:3]) # [start:stop:step]
print(int_list[3:1:-1]) # step 參數如果指定為 -1 可以將 list 的資料順序顛倒
# function
int_list.append(x) 將 x 加入到 list 的末端
int_list.insert(index, x) 將 x 加入到 list 中指定的索引值位置
int_list.pop() 將 list 最末端的資料拋出
del int_list(index) 將指定位置的資料刪除
int_list.sort() 將 list 的資料預設以遞增排序
int_list.sort(reverse=True) 以遞減排序
list_data.index('string') 找值的位置
mylist3.remove('cat') remove

// tuple 多數的特性都與 list 相同，在建立的時候使用小括號 () 將希望儲存的資訊包括起來
# tuple 在索引與切割與 list 部分完全相同
# tuple 與 list 最大的差異在於 tuple 是不可變動（immutable）的資料結構，不具備任何包含新增、刪除與排序資料的操作
int_tuple = tuple(range(11,20))
print(int_tuple)

//dict 除了儲存資料（values）以外，還另外利用標籤（keys）來對資料作索引
# 在建立的時候使用大括號 {} 將希望儲存的資訊包括起來
play_dict = {
    "Fw" : "Robert Kao",
    "Lab": "Leo lin",
    "Direct" : "Jerry Hsu"
}
print(play_dict["Lab"])
print(play_dict.keys())
print(play_dict.values())
print(play_dict.items())
# dict 新增可以直接宣告 dict["key"] = value
# 使用 .keys() 、 .values() 與 .items() 可以分別取出 dict 中的所有標籤（Keys）、所有資料（Values）以及標籤加上資料（Items）

//set 是 Python 較為少用的資料結構，在建立的時候使用大括號 {} 將希望儲存的資訊包括起來，set 只會儲存獨一的資料，若輸入了重複的資訊，則會只記錄一筆
# set 還有一點與其他資料結構很大的差異是，無法使用中括號 [] 做索引或切割
positions = {"G", "G", "F", "F", "C"}
print(type(positions))
print(positions)

// example
play_list = ["Robert Kao", "Leo lin", "Jerry Hsu"]
play_tuple = tuple(play_list)
play_dict = {
    "Fw" : "Robert Kao",
    "Lab": "Leo lin",
    "Direct" : "Jerry Hsu"
}
play_set = set(play_list)

print(type(play_list))
print(type(play_tuple))
print(type(play_dict))
print(type(play_set))
```


## flow control
```python
// if
// and or not (True False)
height = 175
if (height<170):
    print("too low")
elif (height>200):
    print("too high")
else:
    print("height enough")

// for 
// continue 
man_list = ["Robert Kao", "Bill Lin", "Jerry Hsu"]
for man in man_list:
    print(man)
for i in range(3):
    print(man_list[i].split()[1].upper())

// while
man_list = ["Robert Kao", "Bill Lin", "Jerry Hsu"]
i = 0
while (i<3):
    print(man_list[i].split()[1].upper())
    i+=1
```

## 文字檔結構
* **CSV：純文字的方式儲存檔案資料，已逗號分隔資料，可用Microsoft Excel打開檔案。**  

```python
import csv
with open('day06-csv.csv', 'w', newline='') as csvfile:
    writer = csv.writer(csvfile) # 建立 CSV 檔寫入器
    writer.writerow(['股票', '收盤價', '單量'])
    writer.writerow(['台積電', 238, 23])
    writer.writerow(['大同', 40, 121])
    writer.writerow(['華新科', 174, 105])
    
# ---------------------------------------------------------- read

with open('day06-csv.csv', newline='') as csvfile:

  rows = csv.reader(csvfile)  # 讀取 CSV 檔案內容
  for row in rows:  # 以迴圈輸出每一列
    print(row)
```

* **XML：可延伸標記式語言，是一種標記式語言。**

```python
import xml.etree.ElementTree as ET
data = ET.Element('stock') #建立節點stock
tsmc = ET.SubElement(data, 'tsmc')  # 在stock節點底下建立子節點
close = ET.SubElement(tsmc, 'close')  
buy = ET.SubElement(tsmc, 'buy')  
close.set('name','收盤價') # 設定節點的名稱
buy.set('name','單量')  
close.text = '238'  
buy.text = '23'

mydata = ET.tostring(data)  
myfile = open("day06-xml.xml", "wb")  
myfile.write(mydata)  
myfile.close()
    
# ---------------------------------------------------------- read

tree = ET.parse('day06-xml.xml')  
root = tree.getroot()

for elem in root:  
    for subelem in elem:
        print(subelem.get('name'),"----->",subelem.attrib)
```

* **JSON：輕量級的資料交換語言**

```python
# JSON example
{
  "stock": [
    {
      "name": "台積電",
      "close": "238",
      "buy": "23"
    },
    {
      "name": "大同",
      "close": "40",
      "buy": "121"
    },
    {
      "name": "華新科",
      "close": "174",
      "buy": "105"
    }
  ]
}
# --------------------
import json

data = {}  
data['stock'] = []  
data['stock'].append({  
    'name': '台積電',
    'close': '238',
    'buy': '23'
})
data['stock'].append({  
    'name': '大同',
    'close': '40',
    'buy': '121'
})
data['stock'].append({  
    'name': '華新科',
    'close': '174',
    'buy': '105'
})

with open('day06-json.json', 'w') as outfile:  
    json.dump(data, outfile,ensure_ascii=False,indent=2)
    
# ---------------------------------------------------------- read

with open('day06-json.json') as json_file:  
    data = json.load(json_file)
    for p in data['stock']:
        print('股票: ' + p['name'])
        print('收盤價: ' + p['close'])
        print('單量: ' + p['buy'])
        print('')
```

* **YAML：是一個可讀性高，用來表達資料序列的格式**

```python
# YAML example 
stock:
  buy: '121'
  close: '238'
  name: '台積電'
# ------
import yaml
cfg = {
  "stock": dict(
      name='台積電',
      close='238',
      buy='121'
   )  
}
with open("day06_yml.yml", 'w') as outfile:
    yaml.dump(cfg, outfile, default_flow_style=False,allow_unicode=True) 
    
# ---------------------------------------------------------- read

with open("day06_yml.yml", 'r') as yml:
    contents = yaml.safe_load(yml)
    print("取得股票--->",contents['stock'])
```


# package

## datetime
```python
import datetime

# today/now 應該相同
import datetime
current_dt = datetime.datetime.now().strftime("%Y-%m-%d %X")
today = datetime.datetime.today().strftime('%Y%m%d')
# set date 
start = datetime.datetime(2018, 1, 1)
end = datetime.datetime(2018, 8, 1)
```

## beautifulsoup4 - 解析 HTML 資料
* **BeautifulSoup4(selector 分析網頁)**

function     | 說明
-------------|------
prettify()     |美化排版, soup.prettify()
tag_name       |tag data/nest tag data, soup.head, soup.head.title
tag_name.string|tag string, soup.head.title.string
find_all()     |all tag list,  soup.find_all('p')
link.get()     |get 屬性(attribute),link.get('href'), link.get('class')
get_text()     |get text, soup.get_text())

```python
# basic
html_doc = """
<html><head><title>The Dormouse's story</title></head>
<body>
<p class="title"><b>The Dormouse's story</b></p>
<p class="story">Once upon a time there were three little sisters; and their names were
<a href="http://example.com/elsie" class="sister" id="link1">Elsie</a>,
<a href="http://example.com/lacie" class="sister" id="link2">Lacie</a> and
<a href="http://example.com/tillie" class="sister" id="link3">Tillie</a>;
and they lived at the bottom of a well.</p>
<p class="story">...</p>
"""
# ------------
from bs4 import BeautifulSoup
soup = BeautifulSoup(html_doc, "html.parser")
# print(soup)
# prettify() : 美化排版
print(soup.prettify())
# direct get tag data
# .string --> text string
print("tag title :", prettify() : 美化排版)
print("tag head :", soup.head)
print("tag head.title :", soup.head.title)
print("tag head.title.string :", soup.head.title.string)
# find_all() : get all tag
print("tags p :", soup.find_all('p'))
# get() : get 屬性（attribute）
for link in soup.find_all('a'):
    print(link.get('href'), link.get('class'))
# find(id='link3') : find id
print("id link3 :", soup.find(id='link3'))
# get_text() : get text
print("all text :", soup.get_text())
```

```python
import requests
from bs4 import BeautifulSoup

r = requests.get("https://www.imdb.com/title/tt4154796/")
print(r)
# HTML git by text
r_data = r.text
# print(type(r_data))
# print(r_data)
soup = BeautifulSoup(r_data, "html.parser") # parser by html format

sel = soup.select("strong span")
#print(sel)
# get value in float type
for i in sel:
    print(float(i.text))

# get .poster img src value
sel = soup.select(".poster img")
print(sel)
for i in sel:
    print(i.get("src"))
```

* **beautifulsoup4 - example**  

```python
from bs4 import BeautifulSoup
html_str = """
<html>
  <head>
    <title>The Avengers</title>
  </head>
  <body>
    <div id="header">
      <h1>Movies</h1>
    </div>
    <div id="movie-titles">
      <ul>
        <li id="movie-0" class="movies">
          <a href="https://www.imdb.com/title/tt0848228">The Avengers (2012)</a>
        </li>
        <li id="movie-1" class="movies">
          <a href="https://www.imdb.com/title/tt2395427">Avengers: Age of Ultron (2015)</a>
        </li>
        <li id="movie-2" class="movies">
          <a href="https://www.imdb.com/title/tt4154756">Avengers: Infinity War (2018)</a>
        </li>
        <li id="movie-3" class="movies">
          <a href="https://www.imdb.com/title/tt4154796">Avengers: Endgame (2019)</a>
        </li>
      </ul>
    </div>
  </body>
</html>
"""

soup = BeautifulSoup(html_str)
print(soup.find(id="movie-3").find("a").get("href"))
movie = soup.select("li#movie-3 a")
print(type(movie)) # list
print(movie[0]["href"])
```

## requests(抓網頁)
Requests是一個Python HTTP庫

* **requests : disable SSL Warnings - json**  

```python
import requests
import urllib3

# disable SSL Warnings
urllib3.disable_warnings()
r = requests.get("https://opendata.epa.gov.tw/ws/Data/AQI/?$format=json", verify=False)
data_json = r.json()
# print(r.json())
# print(r.status_code)
i=0
for u in data_json:
    i+=1
    print(str(i) + " ***** " + str(u))
```

* **requests : support SSL certificate verify - json**

```python
# support SSL certificate verify
from urllib3 import PoolManager
import json
http = PoolManager()
r = http.request('GET', "https://opendata.epa.gov.tw/ws/Data/AQI/?$format=json")
# print(r.data)    # response data
# print(r.status)  # response status
data_json = json.loads(r.data) # data to json 
#print(data_json)
i=0
for u in data_json:
    i+=1
    # print(str(i) + " ***** " + str(u))
    print(str(i),"*****" ,u["County"] , u["SiteName"], u["PM2.5"])
```

* **requests : html**

```python
import requests
from lxml import etree
from io import BytesIO # bytes to str

r = requests.get("https://opendata.epa.gov.tw/ws/Data/AQI/?$format=xml", verify=False)
tree = etree.parse(BytesIO(r.content))

county = [t.text for t in tree.xpath('//Data/County')]
side_name = [t.text for t in tree.xpath('//Data/SiteName')]
pm25 = [t.text for t in tree.xpath('//Data/PM2.5')]

# zip for 打包成 tuple（元组)
for c, s, p in zip(county, side_name, pm25):
    print(c, s, p)
```


## nbextensions
```python
// 代碼補全 for jupyter notebook(nbextensions) install
conda install -c conda-forge jupyter_contrib_nbextensions

点开 Nbextensions 的选项，并勾选 Hinterland
```

## pandas(資料分析)
Pandas 是 python 的一個數據分析 lib  
Pandas就是建立在Numpy的基礎延伸的套件呢  
資料類型DataFrame:就像是我們在使用的excel表格一樣，是一個二維的數據有index和column  
資料類型Series:是一個類似陣列的物件，裡面可包含陣列的資料  
**資料類型MultiIndex:待研究................**  

function     | 說明
-------------|------
df.head()    |查看前五列觀測值，可以加入參數 n 觀看前 n 列觀測值
df.tail()    |查看末五列觀測值，可以加入參數 n 觀看末 n 列觀測值
df.info()    |查看資料框的複合資訊，包含型別、外觀與變數型別等
df.describe()|查看數值變數的描述性統計，包含最小值、最大值、平均數與中位數等
df.read_csv()   |read csv(accept url)
df.dropna() |remove include NaN data
df.fillna(0)    |NaN fill value
df.sort_values('name') | sort by one field value - 不能改變原變數,要設成另一個變數
isin()     |check include date : employees["Team"].isin(["Legal","Scales","Product"])
notnull()  |value not null : mask = employees["Team"].isnull()
isnull()   |value null : mask = employees["Team"].notnull()
between()  |value between : employees[employees["Start Date"].between("2009-11-10","2010-01-20")]
set_index()|change index : df.set_index("Name", inplace=True),df.set_index( keys =["Pos","Player"], inplace=True)
reset_index() |reset index : df.reset_index(inplace=True)
df.rename()   |change column/index : df.rename( columns/index={"Rk":"Rk1","Age":"Age2",},inplace=True)
drop()        |drop some columns/row-不能改變原變數,要設成另一個變數 : df2 = df.drop(labels=["GS", "MP"], axis="columns")
sort_index()  |sort by index,df.sort_index(inplace=True)
index.get_level_values()|get index name, df.index.get_level_values(0),df.index.get_level_values("Player")
index.set_names()       |change index name, df.index.set_names(["Pos","Name"], inplace=True)
df["Player"].str        |str process, (df["Player"].str.lower(), df["Player"] = df["Player"].str.replace("Ja","Js")
pd.Series()   |create Series
pd.DataFrame()|create data frame,pd.DataFrame(np.random.randn(100, 4), index=pd.date_range('12/31/2017', periods=100), columns=list('ABCD'))
np.abs(df)    |abs 計算整個 DataFrame
se.add(se2)   |+, Searies 相加,對齊不到index都會使用NaN表示, 也可指定特定值　se.add(se2, fill_value = 0)
Pandas-sub(),subtract()|-
Pandas-mul(),multiply()|*
Pandas-truediv(),div(),divide()|/
Pandas-floordiv()|//取整除 - 返回商的整数部分（向下取整）
Pandas-mod()|%
Pandas-pow()|"**",	$a**b 為10的20次方$
pd.concat() |資料合併, pd.concat([ironman1,ironman2], join='inner'))
            |join，outer->聯集、inner->交集(如果資料不存在時有NaN時)
se.append() |append 等同concat只是呼叫更簡單
pd.merge()  |merge 也是合併資料的一種,但可以有更多的應用.....
se.mean()  	|平均值
se.sum()  	|總和
se.min()  	|最小值
se.max()  	|最大值
se.median()	|計算中位數
df.sum()  			|總和,DataFrame進行運算,預設會用欄做計算,如果要改成用列作計算可使用axis ironman_df.sum(axis='columns')
df.count()  		|元素總數
df.first(),last()	|第一個,最後一個元素
df.mean(),median()	|全部平均,中位數平均
df.min(),max()		|最小值,最大值
df.std(),var()		|標準差(Standard Deviation),變異數(Variance)
df.mad()  	    	|平均絕對偏差(Mean Absolute Deviation)
df.prod()  			|元素的積
df.pivot()  		|Return reshaped DataFrame organized by given index / column values-pivot(index=None, columns=None, values=None)
df.groupby("continent").aggregate(['sum', 'max', 'min'])|show 多計算結果
df.groupby("continent").transform(lambda x: x- x.sum()) |將原始資料和計算後的資料作運算(所有可計算欄位)
df.groupby("continent").apply(apply_func)  |使用呼叫函式的方式，可以回傳Pandas物件或是純量(指定欄位)
df.groupby("continent").filter(filter_func)|filter
pd.to_datetime('2019-08-22 17:32:30')|date 變數
pd.to_timedelta(np.arange(5), 'D')   |date offset
pd.to_datetime('2019-08-22 17:32:30')|date 變數
pd.DatetimeIndex(['2018-08-11', ..)  |date for index
pd.date_range('2018-10-11','2018-10-15') |date range generate
pd.eval('df1+df2+df3+df4')         |array 加法(較有效率)
rng=np.random.RandomState(42)      |產生可重現假亂數 依據
pd.DataFrame(rng.rand(100000, 100) |產生 array by RandomState
TSMC.index = pd.to_datetime(TSMC.index) |change index format to datetime*(so support simple date format for index)

variable       | 說明
---------------|------
pd.__version__ |version
df.index       |查看資料框的列索引值
df.shape       |查看資料框的外觀，以 tuple 的型別回傳，(m, n) 表示 m 列觀測值，n 欄變數
df.columns     |查看資料框的變數名稱
df.loc['b']    |index 取出資料,也可取出多個 row : print(df.loc["Michael Jordan"])/print(df.loc[["Michael Jordan", "Dennis Rodman"]])
df.iloc[[0:4]  |get by index position : print(df.iloc[[0,4]]) # index 0 and 4 / print(df.iloc[0:4])  # index 0 to 3
df.T           |將陣列作轉置

* **groupby() - DataFrameGroupBy**

function     | 說明
-------------|------
size()                  |get per grounp counter 
get_group("group_value")|get group data in Dataframe

```python
# Series
# Series，是一個類似陣列的物件，裡面可包含陣列的資料
import pandas as pd
# -----------------------------
my_obj = pd.Series([4,7,-5,3])
print(my_obj)
print(my_obj.values)
print(my_obj.index)
#    RangeIndex(start=0, stop=4, step=1)
# change index not number
my_obj2 = pd.Series([8,9,10,11], index=['a','b','c','d'])
print(my_obj2.index, my_obj2["b"])
#    Index(['a', 'b', 'c', 'd'], dtype='object')
# chack index in 
print('a' in my_obj2)
# change directory to series
dic_data = {'name':'apple','birthday':'1996-1-1','luckynumber':7 }
my_obj3 = pd.Series(dic_data)
my_obj3
#    dtype: object
# Bool list to series
registration = [True,False,True,True]
registration = pd.Series(registration)
registration
#    dtype: bool

# DtatFrame
# DataFrame就像是我們在使用的excel表格一樣，是一個二維的數據有index和column
import pandas as pd
data = {'name': ['Bob', 'Nancy','Amy','Elsa','Jack'],
        'year': [1996, 1997, 1997, 1996, 1997],
        'month': [8, 8, 7, 1, 12],
        'day':[11,23,8,3,11]}
myframe = pd.DataFrame(data)
print(myframe)
# print(myframe["name"][1])
# change columns index
myframe2 = pd.DataFrame(data,columns=['name','year', 'day', 'month'])
print(myframe2)
# add columns (NaN : Not a Number)
myframe3 = pd.DataFrame(data,columns=['name','year', 'month', 'day', 'luckynumber'])
print(myframe3)
# set value
luckynumber = ['3','2','1','7','8']
luckynumber = pd.Series(luckynumber)
myframe3['luckynumber'] = luckynumber
print(myframe3)
# show specific 
print(myframe3['name'])
print(myframe3[['name', 'year']])
print(myframe3['name'][0:4]) # no show index 4
# insert data 
myframe3.insert(3,column="sport",value="Basketball")
print(myframe3)
# sort by one field value - 不能改變原變數,要設成另一個變數
print(myframe3.sort_values('name'))
print(myframe3)

# pandas Series,DataFrame(多個Series),Index(不可修改的陣列)
import pandas as pd
import numpy as np
# set Series(auto index)
ironman = pd.Series([0.11, 0.12, 0.13, 0.14])
print(type(ironman), ironman)
print(ironman.index, ironman.values)
# set Series(index by string)
ironman = pd.Series([0.11, 0.12, 0.13, 0.14], index=['a', 'b', 'c', 'd'])
print(ironman)
# dict create Series
dict_ironman = {
    'a' : 11,
    'b' : 22,
    'c' : 33
}
ironman = pd.Series(dict_ironman)
print(ironman)
# set DataFrame
number = pd.Series({'taipei':200, 'taichung':300, 'changhua':400})
mayor = pd.Series({'taipei': 'Kui', 'taichung': 'Ha', 'changhua': 'Chin'})
ironman_df = pd.DataFrame({'number':number, 'mayor':mayor})
print(ironman_df)
print(ironman_df.index, ironman_df.values, ironman_df.columns)
# dict create DataFrame
dict_ironman_df = {
    'number':{'taipei':201, 'taichung': 301, 'changhua': 401},
    'mayor': {'taipei':'Kui2', 'taichung': 'Ha2', 'changhua': 'Chin2'}
}
ironman_df = pd.DataFrame(dict_ironman_df)
print(ironman_df)
# Index(不可修改的陣列)
ironman_index = pd.Index([0.11, 0.12, 0.13,0.14])
print(type(ironman_index), ironman_index)

# pandas - groupby, sum(), aggregate(), transform(), apply(), filter() 
import pandas as pd
csv_url = "https://storage.googleapis.com/learn_pd_like_tidyverse/gapminder.csv"
df = pd.read_csv(csv_url)
# groupby
# grouped = df[df.year == 2007].groupby("continent")
grouped = df.groupby("continent")
# sum() and aggregate
print(grouped["pop"].sum())
print(grouped["pop"].aggregate(['sum', 'max', 'min']))
# transform - 當需要將原始資料和計算後的資料作運算(所有可計算欄位)
print("----------")
print(df.groupby("continent").transform(lambda x: x- x.sum()))
# apply - 使用呼叫函式的方式，可以回傳Pandas物件或是純量(指定欄位)
print("----------")
def apply_func(x):
    x['pop'] = x['pop'] - x['pop'].sum()
    return x
print(df.groupby("continent").apply(apply_func))
# filter 
print("----------")
def filter_func(x):
    return x['pop'].sum()>6181115304
print(df.groupby("continent").filter(filter_func))
print("----------")
print(df)

# pandas data draw
%matplotlib inline
import pandas as pd
import numpy as np
df = pd.DataFrame(np.random.randn(100,4), index=pd.date_range('12/31/2017', periods=100), columns=list('ABCD'))
print(df)
df.plot()

# show some position data
import pandas as pd
import numpy as np
seriesObj = pd.Series(range(10),index=['a', 'a', 'b', 'b', 'b','c','c','c','c','c'])
seriesObj['c'] 
df = pd.DataFrame(np.random.randn(4,2),index=['a', 'a', 'b', 'b'])
print(df.index)
print(df.loc['b'])

#filter 
mask1 = employees["Team"] != "Marketing"
mask2 = employees["Start Date"] < "1980-01-01"
employees[(mask1 & mask2)] 
mask = employees["Team"].isin(["Legal","Scales","Product"])

# index aligment
import pandas as pd
# ---------------
csv_url = "https://storage.googleapis.com/ds_data_import/stats_per_game_chicago_bulls_1995_1996.csv"
# change index with certain field(1ts)
# df = pd.read_csv(csv_url, index_col="Name")
# change index with certain field(2nd)
df = pd.read_csv(csv_url)
df.set_index("Name", inplace=True)
print(df)
# check index
print(df.index)
# change column/index
df.rename( columns={"Rk":"Rk1",
                  "Age":"Age2",
                 },inplace=True)
df.rename( index={"Scottie Pippen":"Scottie Pippen1",
                  "Luc Longley":"Luc Longley2",
                 },inplace=True)
# drop some columns/row - 不能改變原變數,要設成另一個變數
# axis=1跟axis="columns"是一樣的！axis=0則是和asxis = "row"一樣
# df2 = df.drop(labels=["GS", "MP"], axis="columns")
df2 = df.drop(labels=["GS", "MP"], axis=1)
print(df2)
# get some row
print(df.loc["Michael Jordan"])
print(df.loc[["Michael Jordan", "Dennis Rodman"]])
# get by index position
print(df.iloc[[0,4]]) # index 0 and 4
print(df.iloc[0:4])  # index 0 to 3
# reset index
df.reset_index(inplace=True)
print(df.index)

# groupby() - DataFrameGroupBy
%matplotlib inline 
import pandas as pd
# --------------
csv_url = "https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.csv"
df = pd.read_csv(csv_url)
# print(df.columns)
# type is DataFrameGroupBy
grouped = df.groupby("Pos")
# print(grouped)
# print(type(grouped))
# get per group size
print(grouped.size())
# get group "SF" in pn dtat
print(grouped.get_group("SF"))
# grouped.sum() : get number column sum value

# multi index and index function
%matplotlib inline 
import pandas as pd
# --------------
csv_url = "https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.csv"
df = pd.read_csv(csv_url)
print(df.columns)
print(df["Pos"])
print(df)
# set multiplex
df.set_index( keys =["Pos","Player"], inplace=True)
# sort by index
df.sort_index(inplace=True)
print(df)
print(df["Ht"])
# get 1st index value
print(df.index.get_level_values(0))
# get specific index value
print(df.index.get_level_values("Player"))
# change index name
df.index.set_names(["Pos","Name"], inplace=True)
print(df)
#print(df.index)

# process relative str
%matplotlib inline 
import pandas as pd
# --------------
csv_url = "https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.csv"
df = pd.read_csv(csv_url)
print(df.columns)
#print(df)
#print(df["Pos"])
# Category 是由固定的且有限數量的變量組成的 故較省空間
df["Pos"] = df["Pos"].astype("category")
#print(df["Pos"])
print(df["Player"])
print(df["Player"].str.title())
print(df["Player"].str.lower())
# replace value
df["Player"] = df["Player"].str.replace("Ja","Js")
print(df["Player"])
# check include string
print(df["Player"].str.lower().str.contains("ron"))
# check start string
print(df["Player"].str.lower().str.startswith("js"))
# check end string
print(df["Player"].str.lower().str.endswith("ey"))
# split daya
print(df["Player"].str.split(" "))
print(df["Player"].str.split(" ").get(0))

# support SSL certificate verify
from urllib3 import PoolManager
import json
import pandas as pd

http = PoolManager()
r = http.request('GET', "https://opendata.epa.gov.tw/ws/Data/AQI/?$format=json")
data_json = json.loads(r.data) # data to json 
counties = [i["County"] for i in data_json]
site_name =  [i["SiteName"] for i in data_json]
pm25 =  [i["PM2.5"] for i in data_json]
# print(counties)
# print(site_name)
# print(pm25)

aqi_dict = {
        "County" : counties,
        "SideName" : site_name,
        "pm2.5" : pm25
}
#print(aqi_dict)

# 打包
df = pd.DataFrame(aqi_dict)
print(df)
# save csv file
df.to_csv("aqi.csv", index=False)
# write json file , ensure_ascii=False(show 中文)
with open("aqi.json", "w") as f:
    json.dump(aqi_dict, f, ensure_ascii=False)

# 在 Python pandas 中可以使用 df.loc[m, n] 或 df.iloc[m, n] 兩個方法指定觀測值所在位置
# 兩者用法差在於 df.loc[] 完全憑藉列索引值與欄索引值的標籤；而 df.iloc[] 完全憑藉相對位置
import pandas as pd
# ------------
numbers = [9, 23, 33, 91, 13]
players = ["Ron Harper", "Michael Jordan", "Scottie Pippen", "Dennis Rodman", "Luc Longley"]
df = pd.DataFrame()
df["number"] = numbers
df["player"] = players
print(df)
# ------------
df.index = ["PG", "SG", "SF", "PF", "C"]
print(df.loc[["SG", "SF", "PF"], ["number", "player"]]) # 以索引為準
print(df.iloc[[1, 2, 3], [0, 1]])                       # 以位置為準
# 排序
df.sort_index()                # 依照索引遞增排序
df.sort_index(ascending=False) # 依照索引遞減排序
df.sort_values(by="year").head()                  # 依照 year 遞增排序
df.sort_values(by="year", ascending=False).head() # 依照 year 遞減排序
# 依照 year 遞增排序再依照 continent 遞減排序
df.sort_values(by=["year", "continent"], ascending=[True, False]).head() 

# Python pandas 選擇資料框中特定變數會面對 Series 這樣的資料結構，而 Series 
# 就有完整的摘要方法供我們呼叫，像總和、平均或中位數等
import pandas as pd
csv_url = "https://storage.googleapis.com/learn_pd_like_tidyverse/gapminder.csv"
df = pd.read_csv(csv_url)
df[df.year == 2007]["pop"].sum()

# 在 Python pandas 中我們會使用 .groupby() 方法指定用來分組資料框的文字變數，
# 然後針對變數呼叫摘要方法，分組摘要的結果會以 Series 的型別回傳。
import pandas as pd
csv_url = "https://storage.googleapis.com/learn_pd_like_tidyverse/gapminder.csv"
df = pd.read_csv(csv_url)
grouped = df[df.year == 2007].groupby("continent")
grouped["pop"].sum()

# function iloc
import pandas as pd
df = pd.read_csv("https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996_per_game.csv")
# iloc() 取矩陣範圍資料
df_numerics = df.iloc[:, 4:]

# set for index(field trading_date)
df = df.set_index("trading_date")

# DataFrame only inculde some columns
data = {'names':['a','b','c','d','e'],
        'jan':[133,122,101,104,320],
        'feb':[122,132,144,98,62],
        'march':[64,99,32,12,65] }
df2 = pd.DataFrame(data,columns=['names','jan','feb'])

# pandas - to_datetime, to_timedelta, date_range, eval
import pandas as pd
import numpy as np
# to_datetime
date = pd.to_datetime('2019-08-22 17:32:30')
print(type(date), date)
# to_timedelta
print(date+pd.to_timedelta(np.arange(5), 'D'))
print(date+pd.to_timedelta(np.arange(5), 'Y'))
# date using for index
date_index = pd.DatetimeIndex(['2018-08-11','2018-08-12','2017-08-11','2017-08-12'])
print(type(date_index), date_index)
my_data = pd.Series(np.arange(4),index=date_index)
print(my_data)
print(my_data['2017'])
# create data range
print(pd.date_range('2018-10-11','2018-10-15'))
print(pd.date_range('2018-10-11', periods=5, freq='D'))
# 產生可重現假亂數 依據
rng = np.random.RandomState(42)
# gererate 4 100000*100 array - array add(eval 較有效率)
df1, df2, df3, df4 = (pd.DataFrame(rng.rand(100000, 100)) for i in range(4))
%timeit df1+df2+df3+df4
%timeit pd.eval('df1+df2+df3+df4')
```

* **pandas-read csv說明**

參數      |說明
----------|----
sep       |預設為 , 因為 CSV 檔案就是以逗號（comma）分隔的檔案格式
header    |預設會將 CSV 檔案最上方的一列作為變數名稱，如果 CSV 檔案中沒有變數名稱，需指派 header=None
names     |假如已經指派 header=None 則 names 參數就需要輸入一組變數名稱的 list
skiprows  |指定在讀取時要略過多少列檔案上方的觀測值
skipfooter|指定在讀取時要略過多少列檔案下方的觀測值
nrows     |指定要讀入幾列觀測值
na_values |除了內建的遺漏值種類，還有哪些額外的字元要被視為遺漏值

```python
# 如果我們在 pd.read_csv() 中指定了 skiprows=1、header=None、names=[‘number’, ‘player’, ‘pos’, ‘ht’, ‘wt’, ‘birth_date’, ‘college’] 表示略過本來 CSV 中作為變數名稱的一列、資料中沒有變數名稱並且自行為資料的七個變數命名
csv_url = "https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.csv"
csv_df = pd.read_csv(csv_url, header=None, skiprows=1, names=['number', 'player', 'pos', 'ht', 'wt', 'birth_date', 'college'])
csv_df
```

* **pandas-read txt說明(將來僅用read_csv代替)**

副檔名為 .txt 純文字檔案跟 CSV 檔案的差異就在於分隔符號（separator）  
在 Python 中我們使用 pandas 的 pd.read_table() 方法；值得注意的參數是 sep 預設為 \t 意即 tab 鍵，  
因此面對以分號做為變數分隔的 TXT 檔案就要指定為 sep=";"  
```python
# pd.read_table() 指定 sep=";"
import pandas as pd

txt_url = "https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.txt"
txt_df = pd.read_table(txt_url, sep=";")
txt_df
```

* **pandas-read excel說明( .xlsx or .xls )**  

在 Python 中我們使用 pandas 的 pd.read_excel() 方法  

參數      |說明
----------|----
sheet_name|預設為 0，也就是排序最前面的工作表，可以利用整數來指定載入的工作表，也可以使用工作表名稱來指定
header    |預設為 0，也就是以最上方的一列作為變數名稱，指定 header=None 假如資料中沒有包含變數名稱
names     |假如已經指派 header=None 則 names 參數就需要輸入一組變數名稱的 list
usecols   |選擇哪幾個變數要載入
skiprows  |指定在讀取時要掠過多少列檔案上方的觀測值
skipfooter|指定在讀取時要略過多少列檔案下方的觀測值

```python
# pd.read_excel() 使用預設參數
import pandas as pd

xlsx_url = "https://storage.googleapis.com/ds_data_import/fav_nba_teams.xlsx"
chicsgo_bulls = pd.read_excel(xlsx_url)
chicsgo_bulls

# 例如指定讀取第二個工作表、並選取部分儲存格範圍 A7 至 C16

# pd.read_excel() 指定工作表與讀取範圍
import pandas as pd

xlsx_url = "https://storage.googleapis.com/ds_data_import/fav_nba_teams.xlsx"
boston_celtics = pd.read_excel(xlsx_url, sheet_name='boston_celtics_2007_2008', skiprows=6, header=None, names=['number', 'player', 'pos'], usecols=[0, 1, 2])
boston_celtics
```

* **pandas-read json說明**  

JSON 檔案若是儲存在雲端，利用 requests 模組的 get() 函數搭配 .json() 方法就可以載入，成功之後會以 dict 型別供後續操作。
```python
# JSON 檔案儲存在雲端
from requests import get

json_url = 'https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.json'
chicago_bulls_dict = get(json_url).json()
print(type(chicago_bulls_dict))
chicago_bulls_dict
```

## pandas_datareader.data(get data from web)
pip install pandas_datareader  
import pandas_datareader.data as web  
直接到網路上跟合作的廠商抓資料(無須輸入任何API網址)  
[Remote Data Access list](https://pandas-datareader.readthedocs.io/en/latest/remote_data.html#remote-data-google)  

function     | 說明
-------------|------
DataReader() |read data from seb site, data = web.DataReader("F", 'yahoo', start, end)


```python
# pandas_datareader read and plot
%matplotlib inline
import pandas_datareader.data as web
import datetime
# ------------------------------
start = datetime.datetime(2018, 1, 1)
end = datetime.datetime(2018, 8, 1)
data = web.DataReader("F", 'yahoo', start, end)
# show plot
# print(data)
# data.plot()
# show Colse data
data.plot(y="Close") # also data["Close"].plot() - but if run "data.plot()" no show
# show 2 items
print(data.columns)
data[["High", "Low"]].plot()
```


## lxml
lxml is the most feature-rich and easy-to-use library for processing XML and HTML in the Python language

## pyquery 解析 HTML 資料
conda install pyquery
```python
import requests
from pyquery import PyQuery

r = requests.get("https://www.imdb.com/title/tt4154796/")
print(r)
# HTML git by text
#r_data = r.text
d =  PyQuery(r_data)
#print(d)

# get value
sel = d("strong span").items()
print(sel) # only show point : <generator object PyQuery.items at 0x000002317540BDE0>
print(d("strong span")) # show <span itemprop="ratingValue">8.7</span>
for i in sel:
    print(float(i.text()))
    
# get src
sel = d(".poster img").items()
print(d(".poster img")) 
for i in sel:
    print(i.attr("src"))

#get data for some condition
from pyquery import PyQuery as pq
# -----------
stats_url = "https://www.basketball-reference.com/players/p/piercpa01.html"
html_doc = pq(stats_url)
pts_css = "#per_game .full_table .right:nth-child(30)"
ast_css = "#per_game .full_table .right:nth-child(25)"
reb_css = "#per_game .full_table .right:nth-child(24)"
pts = [float(p.text) for p in html_doc(pts_css)]
ast = [float(a.text) for a in html_doc(ast_css)]
reb = [float(r.text) for r in html_doc(reb_css)]
```

## selenium-操控瀏覽器來擷取 HTML
Seleninm: 它能控制你的瀏覽器,有模有樣地學人類”看”網頁  
conda install selenium  
function(input): clear(), send_key(), submit(), click()
```python
import time
from selenium import webdriver

driver = webdriver.Chrome('./chromedriver')  # Optional argument, if not specified will search path.
driver.get('http://www.google.com/xhtml');
time.sleep(5) # Let the user actually see something!
search_box = driver.find_element_by_name('q')
search_box.send_keys('ChromeDriver')
search_box.submit()
time.sleep(5) # Let the user actually see something!
driver.quit()

# ==== 2nd sample ====
from selenium import webdriver
# open
imdb_home = "https://www.imdb.com"
driver = webdriver.Chrome('./chromedriver')  # Optional argument, if not specified will search path.
driver.get(imdb_home)
print(driver.current_url)
driver.close()
```

## flask
```
// create new environment(include flask and panda)
conda create --name flask python=3 flask pandas
// 載入 flask 工作環境
conda activate flask
// create directory 
mkdir gapminder-api
// get gapminder.csv file 
https://s3-ap-northeast-1.amazonaws.com/sqlite-demo-data/gapminder.csv
// add file 
api.py
// run flask api
python apy.py
// open by browser
http://127.0.0.1:5000
```
* **flask-apy.py**

```python
import flask

app = flask.Flask(__name__)
app.config["DEBUG"] = True

@app.route('/', methods=['GET'])
def home():
        return "<h1>Hello Flask</h1>"
    
app.run()
```

## firebase_admin
Firebase Admin SDK for Python  
// install firebase_admin(conda not support  
pip install firebase_admin  

# Numpy
支援高階大量的維度陣列與矩陣運算，此外也針對陣列運算提供大量的數學函式函式庫  
Numpy是一個提供矩陣運算非常非常非常好用的工具  

function     | 說明
-------------|------
np.array()       |set to ndarray
np.arange(10)  |generate by range
pd.date_range()|set date for pd, index=pd.date_range('12/31/2017', periods=100)
np.ones(5)     |可以創建任意維度和元素個數的數組，其元素值均為1
np.zeros(3,int)|創建的數組元素類型是浮點型的，如果要使用其他類型，可以設置dtype參數進行聲明
		       |np.zeros(4,dtype={'names':('name','number','team'),'formats':('U10','i2','U10')})
np.empty([2,3])|只是它所常見的數組內所有元素均為空，沒有實際意義
np.full((4,2), 2.2) |建立一個arry, 建立一個內容為2.2 4x2 的浮點數陣列
np.linspace()       |建立一個內容介於兩數間的array, np.linspace(-np.pi, np.pi, 100) 
random.randn()  |隨意數+,-,<0,>0...
.random.randint()|整數隨意數, .random.randint(low[, high, size, dtype]) - low (inclusive) to high (exclusive)
.random.random()|隨意數[0,1):>=value<1-,.random.random(size=None),numpy.random.ranf(size=None) also same
.random.normal()|隨意數 for normal (Gaussian) distribution
.random.choice()|a given 1-D array, numpy.random.choice(a, size=None, replace=True, p=None)
np.sin(x\*4\*np.pi)|set to ndarray by sin function
np.abs() |絕對值
np.exp(),exp2(),power()|指數,e^x,2^x,10^x
np.log(),log2(),log10()|對數
.multiply.outer(y,y)|外積
np.mean()  	|平均值
np.sum()  	|總和
np.min()  	|最小值
np.max()  	|最大值
np.cumsum() |回傳累積的數值(array)
np.std()  	|標準差
np.prod		|所有元素的乘積
np.var		|變異量
np.argmin	|找出最小值的索引
np.argmax	|找出最大值的索引
np.median(x)|元素的中位數
np.any		|當陣列中有任一值是True或是非零值時傳回True
np.all		|當陣列中有所有值是True或是非零值時傳回True
np.save('my_array', x)  |save array
np.load('my_array.npy') |load array
myArr = np.loadtxt('my_txt.txt', delimiter=',') |load text file
np.savetxt('txtfile.txt', myArr)                |save text file
df.reshape(4,1)|array 改變維度
np.concatenate([x,y])|concatenate-串接陣列
np.vstack([x,y])     |vstack-垂直串接
np.hstack([x,y])     |hstack-水平串接
np.split(z,[3,5,8])	|split-分割
np.hsplit(z,[2])	|hsplit-垂直分割
np.vsplit(n,[2])	|vsplit-水平分割
np.count_nonzero(x) |no zero number
df.sort()|排序
np.argsort(x)|傳回被排序過的索引值
np.sort(y,axis=0)) |排序依維度 sort by 1st dim
np.random.randint(0,50,size=10)|部分排序:Partitioning
isnull() |檢查空值，回傳布林值 (None,nan)
notnull()|檢查不是空值，回傳布林值
dropna() |刪除空值
fillna() |空值填入特定直,ironman.fillna(0)
np.sort(x)|sort x array
np.average(x)|x array average(same value as mean)
np.percentile(x,25)|百分位數(Percentile)


variable       | 說明
---------------|------
ndim			|維度
shape			|矩陣大小
dtype			|dtype
itemsize		|item bytes
nbytes 			|total bytes
T 				|翻轉維度
base            |相關

**numpy的資料型態有以下幾種***  

字元|說明
----|------
b	|位元組
i	|有號整數
u	|無號整數
f	|浮點數
c	|複數浮點數
S,a	|字串
U	|unicode字串
v	|void

```python
# numpy ndarray
import numpy as np
# direct set vale + set dtype
arr1 = np.array([[1.2, 2.2 ,0.65], [3.2, 34.2 ,5.65]], dtype=complex)
print(arr1)
print(type(arr1[1][2]))
print(arr1[1][2])
# set by list
list1 = [3,7,5]
arr2 = np.array(list1)
print(arr2)
# 維度
print(arr1.ndim, arr2.ndim)
# 矩陣大小
print(arr1.shape, arr2.shape)
# dtype
print(arr1.dtype, arr2.dtype)

# array 相乘,改變維度,一維 + 二維, 翻轉維度,base 
import numpy as np
x = np.arange(4)
y = np.arange(5,9)
# array 相乘
print(x, y, x*y, x*10)
# array 改變維度
x2 = x.reshape(4,1)
print(x, x2)
print(x.shape, x2.shape)
# 一維 + 二維
y2 = np.ones(5)
print(type(y2[0]))
print(y2.shape)
print(y2+x2)
# 翻轉維度
x1 = np.ones([10,2])
y1 = x1.T
print(x1,y1)
# base
x = np.arange(4)
xx = x.reshape(4,1)
print(xx.base in x)

# array 隨意數,平均值,總和,最小值,最大值,累積的數值,標準差
import numpy as np
# 產生隨意數+,-,<0,>0...
print(np.random.randn())
# 產生整數隨意數
# (low, high=None, size=None, dtype='l')
print(np.random.randint(1,10,size=10))
x = np.random.randn(5,4)
print(x)
# print(x.mean(),x.sum(),x.min(),x.max(),x.cumsum(), x.std())
# ----------------
print(x.mean()) # 平均值
print(x.sum())  # 總和
print(x.min())  # 最小值
print(x.max())  # 最大值
print(x.cumsum()) # 回傳累積的數值(array)
# 標準差 std = sqrt(mean(abs(x - x.mean())**2))
# 標準差應用於投資上，可作為量度回報穩定性的指標。標準差數值越大，代表回報遠離過去平均數值，
# 回報較不穩定故風險越高。相反，標準差數值越小，代表回報較為穩定，風險亦較小。
print(x.std()) # 標準差

# numpy- NaN 運算
import pandas as pd
import numpy as np
# ------------------------
ironman1 = np.array([1,2,3,4])
ironman2 = np.array([1,None,3,4])
ironman3 = np.array([1,np.nan,3,4])
print(type(ironman1), ironman1)
print(type(ironman2), ironman2)
print(type(ironman3), ironman3)
#含 NaN 運算 sum()-->nansum(), min()-->nanmin(), max()-->用nanmax()
print(ironman1.sum(), np.sum(ironman1))
print(np.nansum(ironman1))
print(np.nansum(ironman3)) # not support ironman3.nansum(), not accept None

# numpy file control
import numpy as np
x = np.arange(10)
print(x)
# save array and load
np.save('my_array', x)
np.load('my_array.npy')
# save multi array to a file
y = np.arange(10,20)
print(y)
# save multi array and load
np.savez('my_archive.npz', a=x, b=y)
load_a = np.load('my_archive.npz')
print(load_a["a"])
print(load_a["b"])
# load/save text 
myArr = np.loadtxt('my_txt.txt', delimiter=',')
np.savetxt('txtfile.txt', myArr)

import numpy as np
# -----------------
# array
np1 = np.array([1, 2, 3])
np2 = np.array([3, 4, 5])
# 陣列相加
print(np1 + np2) # [4 6 8]
# 顯示相關資訊
print(np1.ndim, np1.shape, np1.dtype) # 1 (3,) int64 => 一維陣列, 三個元素, 資料型別
# 從檔案取資料
# npd = np.genfromtxt('data.csv', delimiter=',')
# start,endm array number
np.linspace(2.0, 3.0, num=5)
# pi
a = np.linspace(-np.pi, np.pi, 100) 
print(a)
# sin
b = np.sin(a)
print(b)
# random : 建立一個 3x3 隨機矩陣
from numpy.random import rand
c = rand(3, 3) 
print(c)

# numpy - random,串接(concatenate),分割(split)
import numpy as np
# .random.random(size=None) [0,1):>=value<1
# .random.random(size=None),numpy.random.ranf(size=None) also same
#- print(np.random.random(3))
#random int : .random.randint(low[, high, size, dtype]) - low (inclusive) to high (exclusive)
ran_int = np.random.randint(0,10,(3,3))
#- print(ran_int)
#- print(ran_int.shape, ran_int.ndim, ran_int.size, ran_int.dtype, ran_int.itemsize, ran_int.nbytes)
# .random.normal(loc=0.0, scale=1.0, size=None)
# random samples from a normal (Gaussian) distribution
# loc Mean (“centre”) of the distribution. - 此概率分佈的均值（對應著整個分佈的中心centre）
# scale Standard deviation (spread or “width”) of the distribution. - 此概率分佈的標準差（對應於分佈的寬度，scale越大越矮胖，scale越小，越瘦高）
# size Output shape
#- print(numpy.random.normal(0,1,(3,3)))
# 串接(concatenate-串接陣列,vstack-垂直串接,hstack-水平串接)
x = np.arange(1,4)
y = np.array([4,5,6])
#- print(np.concatenate([x,y]))
#- print(np.vstack([x,y]))
#- print(np.hstack([x,y]))
# 分割(split-分割,hsplit-垂直分割,vsplit-水平分割)
z = np.arange(1,10)
print(np.split(z,[3,5,8])) # 分割點
print(np.hsplit(z,[2]))
n = z.reshape(3,3)
print(np.vsplit(n,[2]))

# numpy - random,串接(concatenate),分割(split),broadcasting,比較運算子,get some value 
import numpy as np
# .random.random(size=None) [0,1):>=value<1
# .random.random(size=None),numpy.random.ranf(size=None) also same
#- print(np.random.random(3))
#random int : .random.randint(low[, high, size, dtype]) - low (inclusive) to high (exclusive)
ran_int = np.random.randint(0,10,(3,3))
#- print(ran_int)
#- print(ran_int.shape, ran_int.ndim, ran_int.size, ran_int.dtype, ran_int.itemsize, ran_int.nbytes)
# .random.normal(loc=0.0, scale=1.0, size=None)
# random samples from a normal (Gaussian) distribution
# loc Mean (“centre”) of the distribution. - 此概率分佈的均值（對應著整個分佈的中心centre）
# scale Standard deviation (spread or “width”) of the distribution. - 此概率分佈的標準差（對應於分佈的寬度，scale越大越矮胖，scale越小，越瘦高）
# size Output shape
#- print(numpy.random.normal(0,1,(3,3)))
# 串接(concatenate-串接陣列,vstack-垂直串接,hstack-水平串接)
x = np.arange(1,4)
y = np.array([4,5,6])
#- print(np.concatenate([x,y]))
#- print(np.vstack([x,y]))
#- print(np.hstack([x,y]))
# 分割(split-分割,hsplit-垂直分割,vsplit-水平分割)
z = np.arange(1,10)
print(np.split(z,[3,5,8])) # 分割點
print(np.hsplit(z,[2]))
n = z.reshape(3,3)
print(np.vsplit(n,[2]))
# broadcasting
a = np.array([0,1,2])
print(a + 5)
b = np.arange(3)[:, np.newaxis]
print(b)
# 比較運算子(==,!=,<,<=,>,>=)
x = np.array([1,2,3,4,5])
print(x>2)
np.count_nonzero(x>2) # false number
# get some value 
x = np.random.randint(10, size=(4,5))
print(x)
print(x[(x>5) & (x <8)])

# numpy - 排序的索引值,排序,排序依維度,部分排序,建立結構化的資料
import numpy as np
x = np.random.randint(0,100, size=5)
print(x)
# 傳回被排序過的索引值
print(np.argsort(x))
# 排序
x.sort()
print(x)
# 排序依維度
y = np.random.randint(0,100, (4,4))
print(y)
print(np.sort(y,axis=0)) # sort by 1st dim
print(np.sort(y,axis=1)) # sort by 2nd dim
# 部分排序:Partitioning - 最小四個元素放在左邊(順序隨意)
x = np.random.randint(0,50,size=10)
print('x--------------->',x)
print(np.partition(x,4))
# 建立結構化的資料
team =np.zeros(4, dtype={'names':('name','number','team'),'formats':('U10','i2','U10')})
# 建立標題name 資料型別是unicode字串 長度10
# 建立標題number 資料型別是有號整數 長度2
# 建立標題team 資料型別是unicode字串 長度10
print(team)
print(team.dtype)
team['name'] =['彭政閔','林智勝','蘇偉達','陽耀勳']
team['number'] = [23,32,96,23]
team['team'] = ['兄弟象','兄弟象','兄弟象','lamigo']
print(team)
print(team['number'])

# median,percentile
import numpy as np
from scipy import stats
# ------------------
x =np.random.randint(0,100,size=100)
print("x-->",x)
print("x sort-->",np.sort(x))
print("x mean-->",x.mean())
print("x average-->",np.average(x))
print("x median-->",np.median(x))
print("percentile 25-->", np.percentile(x,25))
print("percentile 75-->", np.percentile(x,75))

# 離散型隨機變數(Discrete Random Variable)
import numpy as np
import pandas as pd
# numpy.random.choice(a, size=None, p=None)-Generates a random sample from a given 1-D array
random_list = np.random.choice([1, 2, 3, 4, 5], size=1000, p=[0.25, 0.1, 0.35, 0.2, 0.1])
# Return a Series containing counts of unique values
# sort_index() : sort bt index
print(pd.Series(random_list).value_counts().sort_index())
```

## squarify
pip install squarify  
```python
# 樹狀圖(treemap)
%matplotlib inline 
import pandas as pd
import matplotlib.pyplot as plt
import squarify

csv_url = "https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.csv"
df = pd.read_csv(csv_url)
grouped = df.groupby("Pos")
pos = grouped["Pos"].count()
squarify.plot(sizes=pos.values, label=pos.index, color=["red", "green", "blue", "grey", "yellow"], alpha=0.4)
plt.axis('off')  #不show座標刻度
plt.title("1995-1996 Chicago Bulls roster") # 抬頭
plt.show()
```

## chart-studio --> plotly
pip install chart-studio  
api key = "bEtPpStSQgWRADCmGGe9"  
```python
import chart_studio.plotly as py
import plotly.graph_objs as go
// --------------------------
tsmc = get_ohlc('2330')
# -- show Candlestick fig --
trace = go.Candlestick(x=tsmc.index,
                       open=tsmc["open"],
                       high=tsmc["high"],
                       low=tsmc["low"],
                       close=tsmc["close"])
# no show bottom fig
layout = go.Layout(
    xaxis = dict(
        rangeslider = dict(
            visible = False
        )
    )
)
fig = go.Figure(data=trace, layout=layout)
fig.show()
# update to plotly wibside(need API key)
py.sign_in('kyp001', 'bEtPpStSQgWRADCmGGe9') # Use your own plotly Username / API Key
py.iplot(fig, filename='simple_candlestick')
```

## folium
pip install folium  
```python
```

## scipy
SciPy就是以Numpy為基礎做科學、工程的運算處理的package，包含統計、優化、整合、線性代數、傅立葉轉換圖像等較高階的科學運算  

* *from scipy import stats*  

function     | 說明
-------------|------
stats.mode(x)|眾數(Mode)

```python
# mode 
import numpy as np
from scipy import stats
# ------------------
x =np.random.randint(0,100,size=100)
x_mode = stats.mode(x)
print("x mode-->", x_mode)
print("x mode-->", x_mode.mode[0])
	x mode--> ModeResult(mode=array([10]), count=array([3]))
	x mode--> 10
```

## StatsModels
Statsmodels 是一個 Python 模塊，它為統計數據分析提供了許多機會，例如統計模型估計、執行統計測試等。在它的幫助下，你可以實現許多機器學習方法並探索不同的繪圖可能性。  

## IPython
Ipython是一個python的交互式shell  
from IPython.display import Image  

function     | 說明
-------------|------
IPython.display() |display something
```python
from IPython.display import Image
# show image
Image('figure_sample.png')
```

## sklearn(Scikit-learn)
* **sklearn.tree**

function     | 說明
-------------|------
DecisionTreeClassifier() |create DecisionTreeClassifier
fit()                    |傳入資料
predict()                |預測label
score(X_test,y_test)     |算出準確度

```python
# sklearn.tree 
from sklearn import tree
# 1:皺 0:光滑 
features = [[150,1],[170,1],[130,0],[140,0]]
# 0:橘子 1:蘋果
labels = [0, 0, 1, 1]
clf =tree.DecisionTreeClassifier()
clf = clf.fit(features, labels)
wantPredict = clf.predict([[200,0]])
# return same as label define
print(wantPredict) 
if wantPredict == [1]:
    print('This is an apple')
elif wantPredict == [0]:
    print('This is an orange')
```

* **sklearn.neighbors.KNeighborsClassifier-K-近鄰演算法(K Nearest Neighbor)**

```python
# K-近鄰演算法(K Nearest Neighbor)
from sklearn import datasets
from sklearn.model_selection import train_test_split
from sklearn.neighbors import KNeighborsClassifier
# load 鳶尾花的資料
iris = datasets.load_iris()
# set data abd label variable
iris_data = iris.data
iris_label = iris.target
# 劃分 訓練資料與測試資料
train_data , test_data , train_label , test_label = train_test_split(iris_data,iris_label,test_size=0.2)
# 算出預估結果
knn = KNeighborsClassifier()
knn = knn.fit(train_data,train_label)
print(knn.predict(test_data))
# 列出實際答案比較
print(test_label)
```

* **sklearn.linear_model.LinearRegression 線性迴歸(linear regression)**

```python
# sklearn.linear_model.LinearRegression 線性迴歸(linear regression)
%matplotlib inline
from sklearn.linear_model import LinearRegression
from sklearn import datasets
import matplotlib.pyplot as plt
# generate random data
# sample data=200, feature=1 , label=1, noise設為10，這樣資料會比較分散一點
x,y = datasets.make_regression(n_samples=200, n_features=1, n_targets=1, noise=10)
model = LinearRegression()
model = model.fit(x, y)
predict = model.predict(x[:200,:])
# draw 線性迴歸線
plt.plot(x,predict,c="red")
plt.scatter(x, y)
plt.show()
```

* **sklearn.preprocessing-特徵標準化(normalization) for 提高準確度**
* **sklearn.svm**

```python
# 特徵標準化(normalization) - 提高準確度
# sklearn.svm.SVC
%matplotlib inline
from sklearn import preprocessing
from sklearn.datasets.samples_generator import make_classification
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.svm import SVC
import warnings
# mask warn --> base.py:196: FutureWarning: The default value of gamma will change from 'auto' to 'scale' in version 0.22 
# to account better for unscaled features. Set gamma explicitly to 'auto' or 'scale' to avoid this warning.
#  "avoid this warning.", FutureWarning)
warnings.filterwarnings("ignore", category=FutureWarning, module="sklearn", lineno=196)
X,y = make_classification(n_samples=300, n_features=2, n_redundant=0, n_informative=2,
                         random_state=3, scale=100, n_clusters_per_class=1)
# 標準化
X = preprocessing.scale(X)
# split test data
X_train,X_test,y_train,y_test = train_test_split(X,y,test_size=0.2)
# SVC分類法
clf = SVC()
clf.fit(X_train,y_train)
result = clf.score(X_test,y_test)
print(result)
# show plot
plt.scatter(X[:,0], X[:,1] ,c=y)
plt.show()
```

* **sklearn.model_selection.cross_val_score-交叉驗證**

```python
# 交叉驗證(Cross validation) - 計算多次準確度 - 此為 K-Fold Cross Validation(k交叉驗證)
# 交叉驗證主要分為以下幾類
# k-folder cross-vailation
# kk folder cross-vaildation
# least-one-out cross-validation
# 10-fold corss validation
from sklearn.model_selection import cross_val_score
from sklearn import datasets
from sklearn.neighbors import KNeighborsClassifier
import matplotlib.pyplot as plt
# load 鳶尾花的資料
iris = datasets.load_iris()
# set data abd label variable
X = iris.data
y = iris.target
# change n_neighbors
k_range = range(1,31)
k_score = []
for k_number in k_range:
    knn = KNeighborsClassifier(n_neighbors=k_number)
    # 算出精準度  - 計算多次
    # cv:計算幾次 scoring='accuracy'精準度
    scores = cross_val_score(knn, X,y, cv=10 , scoring='accuracy')
    # print(scores)
    # print(scores.mean())
    k_score.append(scores.mean())
# draw 
plt.plot(k_range, k_score)
plt.xlabel("Neighbors")
plt.ylabel("Score")
plt.show()
```

* **sklearn.externals.joblib - 將訓練的model儲存起來**

```python
# sklearn.externals.joblib - 將訓練的model儲存起來
# load model and save
from sklearn.externals import joblib
from sklearn import datasets
from sklearn.svm import SVC
# load 鳶尾花的資料
iris = datasets.load_iris()
X = iris.data
y = iris.target
# SVC分類法
clf = SVC()
clf.fit(X,y)
#save file
joblib.dump(clf,'clf.pkl')
#load file
clf2 = joblib.load('clf.pkl')
# predict
print(clf2.predict(X[0:10]))
```

* **sklearn.datasets**  

測試資料集  
```python
# load 鳶尾花的資料
iris = datasets.load_iris()
# generate random data
# sample data=200, feature=1 , label=1, noise設為10，這樣資料會比較分散一點
x,y = datasets.make_regression(n_samples=200, n_features=1, n_targets=1, noise=10)
```

* **sklearn.model_selection.train_test_split**  

測試資料劃分
```python
# 劃分 訓練資料與測試資料
train_data , test_data , train_label , test_label = train_test_split(iris_data,iris_label,test_size=0.2)
```

## warnings
mask warning

```python
# mask warning --> base.py:196: FutureWarning: The default value of gamma will change from 'auto' to 'scale' in version 0.22 
# to account better for unscaled features. Set gamma explicitly to 'auto' or 'scale' to avoid this warning.
#  "avoid this warning.", FutureWarning)
import warnings
warnings.filterwarnings("ignore", category=FutureWarning, module="sklearn", lineno=196)

# mask warning -->FutureWarning: Using an implicitly registered datetime converter for a matplotlib plotting method. The converter was registered by pandas on import. Future versions of pandas will require you to explicitly register matplotlib converters.
#To register the converters:
#	>>> from pandas.plotting import register_matplotlib_converters
#	>>> register_matplotlib_converters()
# warnings.warn(msg, FutureWarning)
import warnings
warnings.filterwarnings("ignore", category=FutureWarning, module="pandas")
```

# 基礎視覺化
matplotlib 中的 pyplot 模組、seaborn 模組、pandas 模組**  

## matplotlib
Matplotlib是Python繪圖  
%matplotlib inline  

function     | 說明
-------------|------
plt.show()    |最後畫圖
plt.plot()    |線圖,可同時設多條線, (x,y,color=,marker="o"設定點,linestyle="--" 顯示虛線)
plt.pie()     |圓餅圖
plt.bar()     |長條圖  bar(x, height, width=0.8透明度, bottom=None, *, align='center', data=None, **kwargs)
plt.bar()     |水平長條圖 bar(y, width, height, *args)
plt.errorbar()|誤差圖
plt.hist()    |直方圖
plt.boxplot() |盒鬚圖 pyplot.boxplot(x, *args)
s.plot(kind='kde')|密度圖kde s:Series
plt.subplot(131)|多圖表,(131):1*3 1st,(132):2nd
plt.subplots()  |準備好多個網格 plt.subplots(2, 3, sharex=True, sharey=True)-sharex->是否共享x軸  sharey->是否共享y軸
setp(line1, marker="o", linestyle="--")|set some line configure
plt.title()   |title
plt.xlabel()  |xlabel
plt.ylabel()  |ylabel
plt.xticks()  |x 標示 plt.xticks(np.arange(0, 3)+0.3, ["Math", "Reading", "Scilent"])
plt.yticks()  |y 標示
plt.grid(True)|顯示格線,grid(True, axis='y') only y
plt.text()    |標示文字 text(x, y, s, fontdict=None, withdash=<deprecated parameter>, **kwargs) s=show text
plt.legend()  |顯示數據的名稱 plt.legend(title = "Court") ,plt.legend(loc="upper center", shadow=True)
plt.xlim()    |x 顯示範圍 xlim((left, right), left, right = xlim() - return the current xlim
plt.ylim()    |y 顯示範圍 ylim(bottom, top), bottom, top = ylim()  - return the current ylim
plt.title(".")|抬頭
plt.ases()    |顯示格線
plt.axis('off')  |不show座標刻度
plt.axes([0.65, 0.65, 0.2, 0.2])|標準的axes中顯示另外一個自己定義的axes, plt.axes([bottom, left, width, height])
for item in data |item data : item.get_height(),item.get_x()
plt.figure(figsize=(9, 3))|畫一個圖框 - 9inchs * 3inches

* **linestyle**

值		|描述	|符號
--------|-------|------
solid	|實線	|-
dashed	|虛線	|--
dashdot	|線點	|-.
dotted	|點線	|:
None	|不畫線	|

* **marker：點的形狀，型態**

值		|描述	|符號
--------|-------|------
point			|點			|.
circle			|圓圈		|o
triangle_down	|向下三角形	|v
triangle_up		|向上三角形	|^
triangle_left	|向左三角形	|<
triangle_right	|向右三角形	|>
square		|正方形	|s
pentagon	|五邊形	|p
hexagonl	|六邊形	|h
plus		|加號	|+
x			|打叉	|x
diamond		|鑽石	|D
star		|星號	|*
vline		|豎線

* **linewidth：線的寬度，可以簡寫成lw**

* **legend(\*args)**

值			|描述	|數字
--------	|-------|------
best		|最適宜	|0
upper right	|右上角	|1
upper left	|左上角	|2
lower right	|右下角	|3
lower left	|左下角	|4
right		|右側	|5
center left	|左側中間	|6
center right|右側中間	|7
lower center|下方中間	|8
upper center|上方中間	|9
center		|最適宜		|10


* **matplotlib-->pyplot**

```python
# 誤差圖 - plt.errorbar(x,y..)
%matplotlib inline  
import matplotlib.pyplot as plt
ironman_error_x = np.linspace(-10,10,50)
ironman_error_y = np.random.randint(-10,10,50)
fig = plt.figure()
# ecolor->誤差的顏色  elinewidth->誤差的寬度
plt.errorbar(ironman_error_x, ironman_error_y, yerr=2, fmt='o', color='SteelBlue', ecolor='LightSteelBlue', elinewidth=2)

# matplotlib pyplot plot(線圖 line plot)
%matplotlib inline
import matplotlib.pyplot as plt
years = [1950,1960,1965,1970,1975,1980,
        1985,1990,1995,2000,2005,
        2010,2015]
pops = [2.5,2.7,3,3.3,3.6,4.0,
        4.4,4.8,5.3,6.1,6.5,6.9,7.3]
deaths = [1.2,1.7,1.8,2.2,2.5,2.7,2.9,3,3.1,3.2,3.5,3.6,4]
# x, y list , color=, "--":顯示虛線
# 可同時設多條線
line1 = plt.plot(years, pops, color=(255/255,100/255,100/255))
plt.plot(years, deaths, "--", color=(100/255,100/255,255/255))
# set some for line, marker="o"設定點  linestyle="--" 顯示虛線
plt.setp(line1, marker="o", linestyle="--")
plt.title("Population Growth") # title
plt.xlabel("Year")              # xlabel
plt.ylabel("Population in billions") # yabel
plt.grid(True) # 顯示格線
plt.show()

# matplotlib pyplot plot(線圖 line plot) - draw sin
%matplotlib inline
import numpy as np
import matplotlib.pyplot as plt
# set array for x
x = np.arange(0, 1, 0.01)
# get y array by sin function
y1 = np.sin(x*4*np.pi)
y2 = np.sin(x*2*np.pi)
# print(x)
# print(y1)
# plot and set configure
lines=plt.plot(x,y1,x,y2)
plt.setp(lines,linestyle="--")
plt.show()

# matplotlib pyplot plot(圓餅圖 pie)
%matplotlib inline
import numpy as np
import matplotlib.pyplot as plt
# ------------------------
labels = 'A','B','C','D','E','F'
size = [33,52,12,17,62,48]
separated = (.1,0,0,0,.2,0)
# (size, labels=標示, autopct=顯示百分比, explode=餅分開距離)
plt.pie(size, labels=labels, autopct="%1.1f%%",explode=separated)
# axis('equal')避免比例壓縮為橢圓
plt.axis('equal')
plt.show()

# matplotlib pyplot plot(圓餅圖 pie 2nd) 
%matplotlib inline
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd

data = {'names':['a','b','c','d','e'],
        'jan':[133,122,101,104,320],
        'feb':[122,132,144,98,62],
        'march':[64,99,32,12,65] }
df1 = pd.DataFrame(data)
df1['total'] = df1['jan']+df1['feb']+df1['march']
colors = [(1,.4,.4),(1,.6,1),(.5,.3,1),(.7,.7,.2),(.6,.2,.6)]
# print(df1)
# (size, labels=標示, colors=顏色, autopct=顯示百分比, explode=餅分開距離)
plt.pie(
    df1['total'],
    labels = df1['names'],
    colors = colors,
    autopct='%1.1f%%'
)
plt.axis('equal')
plt.show()

# matplotlib pyplot plot(長條圖 bar) 
%matplotlib inline
import numpy as np
import matplotlib.pyplot as plt
# ------------------
def createLabel(data):
    # data include artist
    # item is patches.Rectangle
    for item in data:
        height = item.get_height() # get Rectangle height
        # text(x, y, s, fontdict=None, withdash=<deprecated parameter>, **kwargs) s=show text
        plt.text(item.get_x(),height*1.05, height)
# ------------------
col_count = 3
A_scores = (553,536,548)
B_scores = (518,523,523)
C_scores = (613,570,588)
D_scores = (475,505,499)

index = np.arange(col_count)
bar_width = 0.2
# (x ,value) simple
# plt.bar(index, A_socres)
# bar(x, height, width=0.8透明度, bottom=None, *, align='center', data=None, **kwargs)[source]
# label:僅為涵義標示(與顯示無關)
A = plt.bar(index, 
        A_scores,
        bar_width,
        alpha=0.2,
        label="K1",
        )
B = plt.bar(index+0.2, 
        B_scores,
        bar_width,
        alpha=0.2,
        label="K2",
        )
C = plt.bar(index+0.4, 
        C_scores,
        bar_width,
        alpha=0.2,
        label="K3",
        )
D = plt.bar(index+0.6, 
        D_scores,
        bar_width,
        alpha=0.2,
        label="K4",
        )
#print(index)
createLabel(A)
createLabel(B)
createLabel(C)
createLabel(D)
# ------------------
plt.grid(True)
plt.xlabel("Subjext")     # show x label
plt.ylabel("Mean score")  # show y label
#print(np.arange(0, 3)+0.3)
# x 標示
plt.xticks(np.arange(0, 3)+0.3, ["Math", "Reading", "Scilent"])
# 加入圖例 plt.legend(title = "Court") 
plt.legend()
# xlim((left, right), left, right = xlim() - return the current xlim
plt.xlim(right=3.5) # x 顯示範圍
# ylim(bottom, top), bottom, top = ylim()  - return the current ylim
plt.ylim(top=700) # y 顯示範圍
plt.show()


# 1st sample
import matplotlib.pyplot as plt
# plot([x], y, [fmt], *, data=None, **kwargs)
# plot([x], y, [fmt], [x2], y2, [fmt2], ..., **kwargs)
# fmt = '[marker][line][color]/[color][marker][line]' format(color,linestyle .. ) -  'ro' for red circles
# set 畫線座標值, set y , x default auto from 0(offset 1)
plt.plot([5, 15, 20, 25])
# set 畫線座標值, set y and x
plt.plot([1, 2, 3, 4], [1, 4, 9, 16], 'ro')
plt.ylabel('some numbers')	# set Y軸 標示
plt.show()	# display a figure

# draw 3 lines
import matplotlib.pyplot as plt
import numpy as np 
# 0 to 5 step 0.2
t=np.arange(0., 5., 0.2)
print(t)
# draw 3 lines
plt.plot(t, t, 'r--', t, t**2, 'bs', t, t**3, 'g^')
plt.show()

# pyplot scatter(條件式畫圖)
import matplotlib.pyplot as plt
import numpy as np
# ------------------
data = {'a': np.arange(50),
        'c': np.random.randint(0, 50, 50),
        'd': np.random.randn(50)}
data['b'] = data['a'] + 10 * np.random.randn(50)
data['d'] = np.abs(data['d']) * 100
# ------------------
# scatter(x, y, s=None, c=None, marker=None, cmap=None, norm=None, vmin=None, vmax=None, alpha=None, linewidths=None, verts=None,
# 		 edgecolors=None, *, plotnonfinite=False, data=None, **kwargs)[source]
# s : scalar or array_like, shape (n, ), optional - The marker size in points**2. Default is rcParams['lines.markersize'] ** 2.
# c : color, sequence, or sequence of color, optional
plt.scatter('a', 'b', c='c', s='d', data=data)
plt.xlabel('entry a')
plt.ylabel('entry b')
plt.show()

# 多圖表(subplot)+統計圖(bar,scatter,plot)
import matplotlib.pyplot as plt
names = ['group_a', 'group_b', 'group_c']
values = [1, 10, 100]
# create figure : width, height in inches
plt.figure(figsize=(9, 3)) # 9inchs * 3inches
# plt.figure() # 640*480
# Add a subplot to the current figure
# nrows, ncols, position
plt.subplot(131)
# Make a bar plot(長條圖)
plt.bar(names, values)
# position #2 畫點
plt.subplot(132)
plt.scatter(names, values)
# position #2 畫折線圖
plt.subplot(133)
# plt.plot(names, values, linewidth=2.0) # change line width
plt.plot(names, values)
# 畫中間抬頭
plt.suptitle('Categorical Plotting')
plt.show()

# 多圖表(subplot)+多lines(plt.plot(t1, f(t1), 'bo', t2, f(t2), 'k'))
import matplotlib.pyplot as plt
import numpy as np
# ---------------
def f(t):
    return np.exp(-t) * np.cos(2*np.pi*t)
# ---------------
t1 = np.arange(0.0, 5.0, 0.1)
t2 = np.arange(0.0, 5.0, 0.02)
# 繪多line
plt.figure()
plt.subplot(211)
# draw 2 line 
plt.plot(t1, f(t1), 'bo', t2, f(t2), 'k')
# cosine wave
plt.subplot(212)
plt.plot(t2, np.cos(2*np.pi*t2), 'r--')
plt.show()

# 直方圖(histogram)-hist +  show text at figure
import matplotlib.pyplot as plt
import numpy as np
# ------------------
mu, sigma = 100, 15
x = mu + sigma * np.random.randn(10000)
# hist(x, bins=None, range=None, density=None, weights=None, cumulative=False, bottom=None, 
#      histtype='bar', align='mid', orientation='vertical', rwidth=None, log=False, color=None, label=None, stacked=False, normed=None, *, data=None, **kwargs)[source]
# n, bins, patches = plt.hist(x, 50, density=1, facecolor='g', alpha=0.75)
#  bins = 50 共有幾條條狀圖, facecolor:color, alpha:透明度, density:是否將得到的直方圖向量歸一化
plt.hist(x, 50, facecolor='g', alpha=0.75)
# title
plt.xlabel('Smarts')
plt.ylabel('Probability')
plt.title('Histogram of IQ')
# show text at figure(依座標) 
plt.text(60, 500, r'$\mu=100,\ \sigma=15$')
# show 格線
plt.grid(True)
plt.show()

# ========= set style ========
# all available style 
plt_themes = plt.style.available
print(plt_themes)
# set style 
# plt.style.use(plt_themes[2])

# ============ 設定說明 ========
# 設定中文字型
from matplotlib.font_manager import FontProperties
myfont = FontProperties(fname="c:/Windows/Fonts/msjh.ttc") #設定字型位置
plt.xlabel("鋒衛位置", fontproperties=myfont)   # X 軸說明
plt.ylabel("球員人數", fontproperties=myfont)   # Y 軸說明
plt.title("反映當時為了抗衡其他具有主宰力中前鋒的隊伍之現象", fontproperties=myfont) # 主標題
plt.suptitle("前場球員為芝加哥公牛隊的大宗", fontproperties=myfont) # 次標題
plt.xticks(range(0, 5), ["中鋒", "大前鋒", "小前鋒", "控球後衛", "得分後衛"], fontproperties=myfont) # 條圖說明

# ====== 加圖上說明 ====== 
# enumerate參數為可遍歷/可叠代的對象(如列表、字符串)
# lst = [1,2,3,4,5,6]
# for index,value in enumerate(lst):
#   print (‘%s,%s‘ % (index,value))
for i, v in enumerate(pos):
  plt.text(i-0.1 , v + 0.4, "{:.1f}".format(v))

# ====== 加入水平線 + 陰影 ====== 
# 10. pandas 模組作圖--長條圖（bar chart） 2nd --> 1st plot line
# 設定水平線
avg_pts = pp_stats["pts"].mean() # 生涯均值
plt.axhline(y = avg_pts, color="g", ls="--", alpha = 0.5) # 水平線
# 設定水平線至上方縣 陰影
plt.fill_between(pp_stats.index, avg_pts, pp_stats["pts"], 
                 where=pp_stats["pts"] >= avg_pts, color="gray",
                 alpha=0.5, interpolate=True) # 陰影

# ====== 調整座標軸 =====
# 10. pandas 模組作圖--長條圖（bar chart） 2nd --> 1st plot line
# 調整 X,Y 軸顯示範圍
plt.xlim(pp_stats.index.min(), pp_stats.index[14]) # 調整軸的範圍
plt.ylim(15, 30) # 調整軸的範圍

# ====== 調整刻度線與刻度線標籤 =====
plt.xticks(range(0, 5), ["中鋒", "大前鋒", "小前鋒", "控球後衛", "得分後衛"], fontproperties=myfont) # 條圖說明
plt.yticks(range(1, 5), range(11,15))
plt.xlabel("Positions")
plt.ylabel("Number of Players")

# ===== 加入圖例 =====
# plt.legend 要加在後面,才會 show 出來
bar_1 = pos.loc[["SG", "PG"]].values
bar_2 = pos.loc[["SF", "PF", "C"]].values
# 若包容多內容設定方法
# bar_1 = pos["Player"].loc[["SG", "PG"]].values
# bar_2 = pos["Player"].loc[["SF", "PF", "C"]].values
plt.bar(range(1, 3), bar_1, label="Back Court", alpha=0.6, color="red")
plt.bar(range(3, 6), bar_2, label="Front Court", alpha=0.6, color="green")
plt.legend(title = "Court") # 加入圖例

# ==== 繪製重疊的直方圖 ====
nba_salary = get_nba_salary()
nba_salary[nba_salary["position"] == "Point Guard"]["salary"].plot.hist(bins = 15, label = "PG")
nba_salary[nba_salary["position"] == "Shooting Guard"]["salary"].plot.hist(bins = 15, label = "SG")
nba_salary[nba_salary["position"] == "Guard"]["salary"].plot.hist(bins = 15, label = "G")
nba_salary[nba_salary["position"] == "Small Forward"]["salary"].plot.hist(bins = 15, label = "SF")
nba_salary[nba_salary["position"] == "Power Forward"]["salary"].plot.hist(bins = 15, label = "PF")
nba_salary[nba_salary["position"] == "Center"]["salary"].plot.hist(bins = 15, label = "C")
plt.legend() # 加入圖例

# ===== 繪製重疊的線圖(line graph) =====
nba_salary = get_nba_salary()
nba_salary[nba_salary["position"] == "Point Guard"]["salary"].plot.line(label = "PG")
nba_salary[nba_salary["position"] == "Shooting Guard"]["salary"].plot.line(label = "SG")
nba_salary[nba_salary["position"] == "Guard"]["salary"].plot.line(label = "G")
nba_salary[nba_salary["position"] == "Small Forward"]["salary"].plot.line(label = "SF")
nba_salary[nba_salary["position"] == "Power Forward"]["salary"].plot.line(label = "PF")
nba_salary[nba_salary["position"] == "Center"]["salary"].plot.line(label = "C")
plt.legend() # 加入圖例

# === 棒棒糖圖（Lollipop）===
# show 點
plt.plot(pos, range(1, pos.size + 1), 'o')
# show 線
# 畫水平線 axhline(y=0, xmin=0, xmax=1, **kwargs)[source]
plt.hlines(y=range(1, points_per_game.size + 1), xmin=0, xmax=pos, color='skyblue')
# show y 
plt.yticks(range(1, pos.size + 1), pos.index)
# x 軸 範圍
plt.xlim(0, 5)
```

## Seaborn
Seaborn 本質上是一個基於 matplotlib 庫的高級 API。它包含更適合處理圖表的默認設置。此外，還有豐富的可視化庫，包括一些複雜類型，如時間串行、聯合分佈圖（jointplots）和小提琴圖（violin diagrams）

function     | 說明
-------------|------
sns.kdeplot()|密度圖
sns.violinplot()|小提琴圖
sns.heatmap()|熱力圖
sns.distplot()|可同時畫出直方圖(hist)和密度圖(kde)
sns.barplot()|長條圖
sns.load_dataset()|load csv file from seaborn
sns.set_style()    |set style - white, dark, whitegrid, darkgrid, ticks
sns.set_context()  |set 圖形大小 - paper, notebook, talk, poster
sns.color_palette()|取得目前調色板的顏色
sns.set_palette()  |設置調色盤的顏色, sns.set_palette(sns.color_palette('bright'))
sns.color_palette()|設置自己定義的調色盤(rgb)-sns.color_palette([(0.45,0.72,0),(0.22,0.34,0),(0.62,1,0.32)])


```python
# seaborn - 直方圖hist + 密度圖kde
%matplotlib inline  
import seaborn as sns
# 直方圖hist + 密度圖kde
ironman_series = pd.Series(np.random.randn(1000))
sns.distplot(ironman_series)

# seaborn - load from seaborn,長條圖(bar),style,圖形大小,調色板的顏色
%matplotlib inline  
import seaborn as sns
import pandas as pd 
import numpy as np
# load flights.csv from seaborn
ironman_df = sns.load_dataset('flights')
# resharped df
ironman_df = ironman_df.pivot(index='month', columns='year', values='passengers')
# set style - white, dark, whitegrid, darkgrid, ticks
sns.set_style('darkgrid')
# set 圖形大小 - paper, notebook, talk, poster
sns.set_context('paper')
# 長條圖 bar(x=index, y=value)
sns.barplot(ironman_df.sum().index,ironman_df.sum().values)
# 取得目前調色板的顏色
sns.palplot(sns.color_palette())

# 密度圖（Density plot）
%matplotlib inline 
import matplotlib.pyplot as plt
import seaborn as sns
nba_salary = get_nba_salary()
sns.kdeplot(nba_salary['salary'], shade=True)
plt.show()

# 密度圖（Density plot）- 重疊
# get only top 100 player more clear
nba_salary = get_nba_salary()
salary_pos = nba_salary.pivot(index='player', columns='position', values='salary')
colors = ["r", "g", "b", "c", "m","r" , "g", "b"]
print(salary_pos)
# get any position 1 item
positions = nba_salary["position"].unique()
print(positions)
for color, pos in zip(colors, positions):
    # notna() : not include NaN
    sns.kdeplot(salary_pos[pos][salary_pos[pos].notna()], shade=True, color=color, alpha = 0.5)

# ====== 小提琴圖 ========
# get only top 100 player more clear
nba_salary = get_nba_salary()
sns.violinplot(x=nba_salary["position"], y=nba_salary["salary"])

# 熱力圖(heatmap)
%matplotlib inline 
import numpy as np
import seaborn as sns
# ---------------------------
# rand() 僅正值
uniform_data = np.random.rand(10, 12)
# randn() 含正負值
normal_data = np.random.randn(10, 12)
# seaborn.heatmap(data, vmin=None, vmax=None, cmap=None, center=None, robust=False, annot=None, fmt='.2g', 
#   annot_kws=None, linewidths=0, linecolor='white', cbar=True, cbar_kws=None, cbar_ax=None, square=False, 
#   xticklabels='auto', yticklabels='auto', mask=None, ax=None, **kwargs)
#  annot = True ,write the data value in each cell.
#  fmt = string format
#  linewidths = Width of the lines that will divide each cell
#  cmap : map to different color
#  cbar=False Don’t draw a colorbar
# -- change color range --
#* ax = sns.heatmap(uniform_data, vmin=0, vmax=1)
# -- 色系中間為 0 --
#* ax = sns.heatmap(normal_data, center=0)
# -- load 1 file for test --
# load .csv file from https://github.com/mwaskom/seaborn-data
flights = sns.load_dataset("flights")
# DataFrame.pivot(index=None, columns=None, values=None)
# index=month columns=year values=passengers
flights = flights.pivot("month", "year", "passengers")
#* ax = sns.heatmap(flights)
#* ax = sns.heatmap(flights, annot=True, fmt='d')
#* ax = sns.heatmap(flights,linewidths=.5, cmap="YlGnBu")
ax = sns.heatmap(flights, center=flights.loc["June", 1955], cbar=False)
```

## bokeh(draw by HTML)
conda install bokeh  
from bokeh.plotting import figure, show  
> ===== 其他圖形 =====  
> bokeh.charts.Bar — 製作長條圖  
> bokeh.charts.BoxPlot — 製作盒鬚圖  
> bokeh.charts.HeatMap — 製作熱圖  
> bokeh.charts.Donut — 製作甜甜圈圖  
> ===== Bokeh 也提供了排版專用的工具 =====  
> Horiontal Layout / 水平式版面 ( hplot )  
> Vertical Layout / 垂直式版面 ( vplot )  
> Grid Layout / 格式排版 ( gridplot )  
> Form Layout / 表單排版 (formplot )  

function     	| 說明
-------------	|------
p = figure() 	|設繪圖板大小
p.circle() 		|畫圓
p.line() 		|畫線
p.multi_line()	|multi line
p.vbar() 		|bar(長條圖)
p.patches() 	|patch(多邊形)
show(p)			|最後畫圖

```python
# draw by HTML
from bokeh.plotting import figure, show, output_file
# 設定輸出檔名
output_file("out.html")
# 設繪圖板大小
p = figure(plot_width=500, plot_height=500)
x = [1,2,3,4,5,6,7,8,9,10,11]
y = [6,3,7,2,4,6,1,2,3,5,6]
# 畫圓
p.circle(x, y, size=20, color="gray", alpha=0.6)
# 畫線
p.line(x, y, line_width=3)
# multi line
x1 = [1, 2, 3]
x2 = [2, 3, 4, 5, 6]
y1 = [3, 2, 5]
y2 = [3, 2, 4, 1, 3]
p.multi_line([x1,x2] , [y1, y2],
             color=["firebrick", "navy"], alpha=[0.8, 0.3], line_width=5)
# bar(長條圖)
p.vbar(x=[1, 2, 3, 4], width=0.5, bottom=0,
       top=[1.2, 2.5, 3.7, 2.9], color="black",alpha=0.4)

# patch(多邊形)
x1 = [1, 4, 5, 2]
x2 = [3, 4, 5, 6]
x3 = [1,3,2]
y1 = [2, 3, 5, 6]
y2 = [4, 7, 7, 5]
y3 = [7,8,5.5]
p.patches([x1,x2,x3 ], [y1,y2,y3],
          color=["black", "navy","firebrick"], alpha=[0.2, 0.2,0.3], line_width=2)
show(p)
```

## base plotting system

## ggplot2


# Warning 

## No module named 'sklearn.cross_validation'
```python
# cross_validatio不再使用了,劃分到 model_selection
from sklearn.model_selection
```


# 分析

## sklearn
```python
# 取測試資料
# model_selection中train_test_split()函式
# X_train, X_test, y_train, y_test = train_test_split(train_data, train_target, test_size, random_state，shuffle)
# train_data：待劃分的樣本資料
# train_target：待劃分的對應樣本資料的樣本標籤
# test_size：1）浮點數，在0 ~ 1之間，表示樣本佔比（test_size = 0.3，則樣本資料中有30%的資料作為測試資料，記入X_test，其餘70%資料記入X_train，同時適用於樣本標籤）；
#            2）整數，表示樣本資料中有多少資料記入X_test中，其餘資料記入X_train
# random_state：隨機數種子，種子不同，每次採的樣本不一樣；種子相同，採的樣本不變（random_state不取，取樣資料不同，但random_state等於某個值，取樣資料相同，取0的時候也相同，這可以自己程式設計嘗試下，不過想改變數值也可以設定random_state = int(time.time())）
# shuffle：洗牌模式，
#            1）shuffle = False，不打亂樣本資料順序；2）shuffle = True，打亂樣本資料順序
# --------------
# from sklearn.model_selection import train_test_split
# train_df, validation_df = train_test_split(labeled_df, test_size=0.3, random_state=123)

# model_selection中train_test_split 2nd example
import numpy as np
from sklearn.model_selection import train_test_split
X, y = np.arange(30).reshape((10, 3)), range(10) 
X_train, X_test ,y_train, y_test= train_test_split(X, y,test_size=0.3, random_state = 20, shuffle=True)
```

## 統計分析
描述統計(Descriptive Statistics)  
推論統計(Inferential Statistics)  
定性數據(Qualiative Data)：對事物性質進行描述數據  
定量數據(Quantitative Data)：事物數量特徵的數據，由數字所組成。  

### 數據的位置
* 樣本平均數(Sample Mean)  
算術平均數(Arithmetic Mean):加總後平均  
幾何平均數(Geometric Mean)  
* 中位數(Median)
將樣本從小到大做排序，如果樣本是奇數個中位數即為最中間的值，如果是偶數個，中位數是中間兩個數值的平均  
* 眾數(Mode)  
樣本中出現次數最多的數值  
* 百分位數(Percentile)  
統計學中經常將25百分位數、中位數和75百分位數組成四分位數(Quartile)。25百分位數叫做第一四分位數(下四分位數)、中位數為第二四分位數、75百分位數為第三四分位數(上四分位數)  

### 數據的離散度
* 全距(Range)  
指的是數據中的最大值和最小值，公式為：  
全距 = 最大值 - 最小值  
* 平均絕對偏差(Mean Absolute Deviation)  
採用的方式是用樣本與平均值(Mean)的差值來計算，當差值越大則表示數據值偏離均值越遠。這邊需要注意到的是平均偏差(Mean Deviation)的相加為0，所以需要加上絕對值來運算。  
$$M_{D}=\cfrac{1}{n}\sum_{i=1}^n|x_{i}-\bar x|$$
* 變異數(Variance)  
變異數也是用來描述數據的離散程度  
$$s^2=\cfrac{\displaystyle \sum_{i=1}^n(x_{i}-\bar x)^2}{n-1}=\cfrac{\displaystyle \sum_{i=1}^nx^2_i-n\bar x^2}{n-1}$$
* 標準差(Standard Deviation)  
標準差就是變異數得平方根  
$$s=\sqrt{\cfrac{\displaystyle \sum_{i=1}^n(x_{i}-\bar x)^2}{n-1}}$$
```python
# 數據的離散度
import pandas as pd
ser_data = pd.Series([60,70,80,80,90,100])
print("平均值", ser_data.mean())
print("全距", ser_data.max()-ser_data.min())
print("平均絕對偏差", ser_data.mad())
print("變異數", ser_data.var())
print("標準差", ser_data.std())
```

### 統計學基礎 - 隨機變數(Random Variable)
離散型隨機變數(Discrete Random Variable)：隨機變數取值的範圍有限個(ex 擲硬幣只有兩種結果，所以取擲的範圍有限制)  
連續型隨機變數(Continuous Random Variable)：隨機變數可以在一個區間上任意取值(ex 股票中的收益率就是連續型隨機變數)  

## 均方誤差（Mean Square Error）


# API or url

## 1.stock information
```
// 某月份某檔股票資料
https://www.twse.com.tw/exchangeReport/STOCK_DAY?response=html&date=20130501&stockNo=1423
https://www.twse.com.tw/exchangeReport/STOCK_DAY?response=json&date=20130501&stockNo=1423
// csv download
https://www.twse.com.tw/exchangeReport/STOCK_DAY?response=csv&date=20130501&stockNo=1423
// 上市
http://www.tpex.org.tw/web/stock/aftertrading/daily_trading_info/st43_result.php?d=107/08&stkno=3105

# read stock from yahoo
import requests
# period1是指起始時間，而period2是指結束時間，其單位為1970的過了n秒
site = "https://query1.finance.yahoo.com/v7/finance/download/2330.TW?period1=0&period2=1566573921000&interval=1d&events=history"
response = requests.post(site)
print(response.text)

# read csv file
import pandas as pd
# set index by Date
TSMC = pd.read_csv('stock_2330_20190823.csv', index_col='Date')
# change index format to datetime*(so support simple date format for index)
TSMC.index = pd.to_datetime(TSMC.index)
# print(TSMC.Open["2016"])
```

# tool

## 1. python2 to python3

```
// C:\Users\RobertKao\AppData\Local\Programs\Python\Python37\Tools\scripts\2to3
#會產生一個script.py -> Python3 script.py.bak -> Python2
2to3 -w script.py
```  

# example

## 1. get title

```python
import requests
from bs4 import BeautifulSoup
r = requests.get("https://www.ptt.cc/bbs/MobileComm/index.html") # get page
# print(r.text) # print HTML

soup = BeautifulSoup(r.text, "html.parser") # parser by html format
sel = soup.select("div.title a") # get <div class="title"></div>'s <a>'
# print(sel)

# print href and title
for s in sel:
    print(s["href"], s.text)
```

**send cookie for over 18 + file access**
```python
import requests
from bs4 import BeautifulSoup

# prepare get cookie
r = requests.session()
# set payload data
payload = {
    "from":"/bbs/Gossiping/index.html",
    "yes":"yes"
}
r1 = r.post("https://www.ptt.cc/ask/over18?from=%2Fbbs%2FGossiping%2Findex.html", payload)
r2 = r.get("https://www.ptt.cc/bbs/Gossiping/index.html")

soup = BeautifulSoup(r2.text, "html.parser") # parser by html format
sel = soup.select("div.title a") # get <div class="title"></div>'s <a>'

# file access
# flag : r/w/b(binary)/a(add)
f = open("file.txt", "w")

# print href and title
for s in sel:
    print(s["href"], s.text)
    # file write
    f.write(str(s["href"]) + s.text + "\n")

# file close
f.close()

print("dump file ...")
# file open
f = open("file.txt", "r")
rf = f.read()
print(rf)
# file close
f.close()
```

## 2. get page up

```python
import requests
from bs4 import BeautifulSoup
url = "https://www.ptt.cc/bbs/MobileComm/index.html"
for i in range(3):
    r = requests.get(url) # get
    soup = BeautifulSoup(r.text, "html.parser") # parser html
    sel = soup.select("div.title a") # get <div class="title"></div>'s <a>'
    u = soup.select("div.btn-group.btn-group-paging a") # get <div class="title"></div>'s <a>'
    print("page", i,":" , url)
    for s in sel:
        print(s["href"], s.text)
    url = "https://www.ptt.cc" + u[1]["href"] # get 2nd(up page) href
```

## 3. get picture

```python
import requests

# get image 
pic = requests.get("https://imgur.dcard.tw/N2k5kV2.jpg")
# open file
f = open("img1.png", "wb")
# write image content to file
f.write(pic.content)
f.close()

print("save image ...")
```

## 4. get mutiple picture

```python
import requests
from bs4 import BeautifulSoup
import json

# open file for log
test = open("spider/pet/test.txt","w",encoding='UTF-8')

# get page
p = requests.Session() # request include get cookie
url = requests.get("https://www.dcard.tw/f/pet") # get
soup = BeautifulSoup(url.text, "html.parser") # parser html
# print(soup)

# get search item link
sel = soup.select("div.PostListPage_topicListWrapper_Iw1Nao a.TopicList_topic_1XGOjs")
a = []
query_data = sel[2].text # get text --> 貓
# print(query_data, "...")
for s in sel:
    # print(s["href"])
    a.append(s["href"])

# search a[2] : 貓 page
# url = "https://www.dcard.tw" + a[2]
# print(url) # show page link address

# params
post_data={
    "field":"topics",
    "query": query_data,
    "sort":"created",
    "offset":"30",
    "since":"0"
}

'''
headers : can not add
head_data = { "Referer": "https://www.dcard.tw/", "User-Agent": "Mozilla/5.0" }
r = p.get("https://www.dcard.tw/_api/search/posts", params=post_data, headers=head_data)
'''

# show page 0 to 1 title
for k in range(0,2):
    # print("page ", k)
    post_data["offset"] = str(k*30)
    r = p.get("https://www.dcard.tw/_api/search/posts", params=post_data)
    # json to text 
    data2 = json.loads(r.text)
    for u in range(len(data2)):
        temp_url = "/f/pet/p/" + str(data2[u]["id"]) + "-"+ data2[u]["title"].replace(" ","-")
        a.append(temp_url)

# save and show all page link address
j=0
q=0
for i in a[2:]:
    url = "https://www.dcard.tw"+i
    j+=1
    print ("第",j,"頁的URL為:"+url)
    test.write("第 {} 頁的URL為: {} \n".format(j,url))
    url=requests.get(url)
    soup = BeautifulSoup(url.text,"html.parser")
    sel_jpg = soup.select("div.PostPage_content_1JHbeJ div div img.GalleryImage_image_3lGzO5")
    # save and show all image
    for c in sel_jpg:
        # check include "https" is correct address
        if ( "https" in c["src"] ):
            q+=1
            print("第",q,"張:",c["src"])
            test.write("%\n""第 {} 張: {} \n".format(q,c["src"]))
            # get image and write
            pic = requests.get(c["src"])
            f = open("spider/pet/" + str(q) + ".png", "wb")
            f.write(pic.content)
            f.close()

test.close()
print(".....end")
```

## 5. get mutiple movie information by selenium

```python
from pyquery import PyQuery
from selenium import webdriver

# give movie information
def get_movie_info(movie_url):
    """
    get movie info from IMDB
    """
    # pyquery 解析
    d = PyQuery(movie_url)
    movie_rating = float(d("strong span").text())
    movie_genre = [x.text() for x in d(".subtext a").items()]
    movie_release_date = movie_genre.pop()
    movie_poster = d(".poster img").attr("src")
    movie_cast = [x.text() for x in d(".primary_photo+ td a").items()]
    
    """
    print(movie_rating)
    print(movie_genre)
    print(movie_release_date)
    print(movie_poster)
    print(movie_cast)
    print(d)
    """
    movie_info = {
        "movieRating" : movie_rating,
        "movieGenre" : movie_genre,
        "movieReleaseDate" : movie_release_date,
        "moviePosterLink" : movie_poster,
        "movieCast" : movie_cast,
    }
    return movie_info;

def get_movies(*args):
    """
    get multiple movie
    """
    # open web
    imdb_home = "https://www.imdb.com"
    driver = webdriver.Chrome('./chromedriver')  # Optional argument, if not specified will search path.
    
    movies = dict()
    for movie_title in args:
        # to home
        driver.get(imdb_home)
        # find search itel
        search_elem = driver.find_element_by_xpath("//input[@id='navbar-query']")
        search_elem.send_keys(movie_title)
        # click() search
        driver.find_element_by_xpath("//button[@id='navbar-submit-button']").click()
        # click 1st movie
        driver.find_element_by_xpath("//tr[@class='findResult odd'][1]/td[@class='primary_photo']/a").click()
        # get movie info
        movie_info = get_movie_info(driver.current_url)
        movies[movie_title] = movie_info
        
    # close browse
    driver.close()
    return movies

# show movie information
# return_msg = get_movie_info("https://www.imdb.com/title/tt4154796")
# print(return_msg)

# show multiple movie information
movie_msg = get_movies("Avengers: Endgame", "Captain Marvel")
print(movie_msg)
```

## 6. stock high price list

```python
import requests
from bs4 import BeautifulSoup
import pandas
import datetime

# hot stock for listed company
# e=tse, otc
def get_hot_stock():
    stock_types = ["tse", "otc"]
    stock_list = ["https://tw.stock.yahoo.com/d/i/rank.php?t=pri&e={}&n=100".format(st) for st in stock_types]
    current_dt = datetime.datetime.now().strftime("%Y-%m-%d %X")
    current_dts = [current_dt for _ in range(200)]
    ids = []
    names = []
    prices = []
    amounts = []
    mkt_values = []
    
    for get_url in stock_list:
        r = requests.get(get_url)
        soup = BeautifulSoup( r.text, "html.parser") # parser by html format
        sel = soup.select("tr tbody tr")
        for i in range(len(sel)):
            if i<=1:
                continue
            row_data = sel[i].text.split()
            ids.append(row_data[1])
            names.append(row_data[2])
            prices.append(float(row_data[3]))
            amounts.append(int(row_data[9].replace(",", "")))
            mkt_values.append(float(row_data[10])*100000000)
    types = ["上市" for i in range(100)] + ["上櫃"for i in range(100)]
    ky_regists = [True if "KY" in st else False for st in names]
    
    # 打包
    df = pandas.DataFrame()
    df["scrapingTime"] = current_dts
    df["type"] = types
    df["kyRegistered"] = ky_regists
    df["ticker"] = ids
    df["stock"] = names
    df["price"] = prices
    df["volume"] = amounts
    df["mktValue"] = mkt_values
    return df

# dump hot stock
price_ranks = get_hot_stock()
print(price_ranks.shape) # show rows × columns
# price_ranks.head() # show head 5
# price_ranks.tail() # show tail 5
price_ranks # middle show ...
```

## 7. flask get data(web api)
http://127.0.0.1:5000  
http://127.0.0.1:5000/cities/all  
```python
import flask
from flask import jsonify

app = flask.Flask(__name__)
app.config["DEBUG"] = True
# show chinese
app.config["JSON_AS_ASCII"] = False

# test data
tpe = {
"id": 0,
	"city_name": "台北",
	"country_name": "台灣",
	"is_capital": True,
	"location": {
		"longitude": 121.569649,
		"latitude": 23.03786
	}
}
nyc = {
	"id": 1,
	"city_name": "New York",
	"country_name": "United States",
	"is_capital": False,
	"location": {
		"longitude": -74.004364,
		"latitude": 40.710405
	}
}
ldn = {
	"id": 2,
	"city_name": "London",
	"country_name": "United Kingdom",
	"is_capital": True,
	"location": {
		"longitude": -0.114089,
		"latitude": 51.507497
	}
}
cities = [tpe, nyc, ldn]

@app.route('/', methods=['GET'])
def home():
	return "<h1>Hello Flash</h1>"

@app.route('/cities/all', methods=['GET'])
def city_all():
	return jsonify(cities)

app.run()
```

## 7. flask get data(web api-get csv file data)
http://127.0.0.1:5000  
http://127.0.0.1:5000/gapminder/all  
```python
import flask
from flask import jsonify
import pandas

app = flask.Flask(__name__)
app.config["DEBUG"] = True
# show chinese
app.config["JSON_AS_ASCII"] = False

# get gapminder csv
pd = pandas.read_csv('./gapminder.csv') 
gapminder_data = pd.get_values() # get csv data

gapminder_list = []
row_no = int(pd.shape[0])
column_no = int(pd.shape[1])
for i in range(row_no):
	row_dict = {}
	for j in range(column_no):
		row_dict[pd.columns[j]] = gapminder_data[i][j]
	gapminder_list.append(row_dict)

@app.route('/', methods=['GET'])
def home():
	return "<h1>Hello Flash</h1>"

@app.route('/gapminder/all', methods=['GET'])
def gapminder_all():
	return jsonify(gapminder_list)

app.run()
```

## 8. flask get data(web api-get csv file for specific country)
http://127.0.0.1:5000  
http://127.0.0.1:5000/gapminder/all  
http://127.0.0.1:5000/gapminder?country=Taiwan  
http://127.0.0.1:5000/gapminder?country=Austria  
```python
import flask
# add request for get parameter
from flask import jsonify,request
import pandas

app = flask.Flask(__name__)
app.config["DEBUG"] = True
# show chinese
app.config["JSON_AS_ASCII"] = False

# get gapminder csv
pd = pandas.read_csv('./gapminder.csv') 
gapminder_data = pd.get_values() # get csv data

gapminder_list = []
row_no = int(pd.shape[0])
column_no = int(pd.shape[1])
for i in range(row_no):
	row_dict = {}
	for j in range(column_no):
		row_dict[pd.columns[j]] = gapminder_data[i][j]
	gapminder_list.append(row_dict)

@app.route('/', methods=['GET'])
def home():
	return "<h1>Hello Flash</h1>"

@app.route('/gapminder/all', methods=['GET'])
def gapminder_all():
	return jsonify(gapminder_list)

# get specific country
@app.route('/gapminder', methods=['GET'])
def gapminder_country():
	if 'country' in request.args:
		country = request.args['country']
	else:
		return "Error: No country provided. Please specify a country."

	results = []
	for elem in gapminder_list:
		if elem['country'] == country:
			results.append(elem)
	return jsonify(results)

app.run()
```

## 9. firebase test
// install firebase_admin(conda not support  
pip install firebase_admin  
```python
import firebase_admin
from firebase_admin import credentials

from firebase_admin import db
from requests import get

#init firebase
cred = credentials.Certificate("./my-pythone-test-db-firebase-adminsdk-hshx2-1cad43354a.json")
firebase_admin.initialize_app(cred, {
    'databaseURL' : 'https://my-pythone-test-db.firebaseio.com/' # 替換成自己的 Firebase 網址
})

# get json file
json_url = 'https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.json'
chicago_bulls_dict = get(json_url).json()

# add data to DB
root = db.reference()
root.child('chicago_bulls').push(chicago_bulls_dict)

# get data from DB
ref = db.reference('chicago_bulls')
chicago_bulls = ref.get()
chicago_bulls
```

## 10. pandas 模組作圖--長條圖（bar chart）
plot.bar()
```python
# Series show bar
import pandas as pd
import matplotlib.pyplot as plt
# ------------------
csv_url = "https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.csv"
df = pd.read_csv(csv_url)
grouped = df.groupby("Pos")
pos = grouped["Pos"].count()
# Series show bar
# Series.plot.bar(self, x=None, y=None, **kwargs)[source]
pos.plot.bar()
# show y tick location : yticks(ticks, [labels], **kwargs) 
plt.yticks([1, 2, 3, 4], [1, 2, 3, 4])
plt.show()

# show group 平均值圖
%matplotlib inline 
import pandas as pd
import matplotlib.pyplot as plt
# ------------------
play_info_url = "https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.csv"
per_game_url = "https://storage.googleapis.com/ds_data_import/stats_per_game_chicago_bulls_1995_1996.csv"
play_info = pd.read_csv(play_info_url)
per_game = pd.read_csv(per_game_url)
# merge play_info and per_game 
play_info_mix = play_info.merge(per_game, left_on='Player', right_on='Name' )
# group by Pos
grouped = play_info_mix.groupby("Pos")
# group "PTS/G" mean(平均值)
# print(grouped["PTS/G"].mean())
pos_pstg_mean = grouped["PTS/G"].mean()
print(pos_pstg_mean)
# plot by bar
pos_pstg_mean.plot.bar()
plt.show()
```

## 11. pandas 模組作圖--直方圖（bar histogram)
```python
# NBA 薪水分布圖
%matplotlib inline 
import requests
from bs4 import BeautifulSoup
import pandas as pd
import matplotlib.pyplot as plt

def get_nba_salary():
    # chaget to post + payload get morether 100
    payload = {
        "ajax":"true",
        "mobile":"false"
    }
    # r = requests.get("https://www.spotrac.com/nba/rankings/") # only get 100 items
    r = requests.post("https://www.spotrac.com/nba/rankings/", payload)
    # get(text format) parser
    soup = BeautifulSoup(r.text, "html.parser") # parser by html format
    # select process
    salarys = [p.text.replace(",", "") for p in soup.select("td.rank-value span.info")]
    salarys = [int(p.replace("$", "")) for p in salarys]
    players = [p.text for p in soup.select("td.rank-name h3 a")]
    positions =  [p.text for p in soup.select("td.rank-name span.rank-position")]
    # print(salary)
    # print(player)
    # print(position)
    df = pd.DataFrame()
    df["player"] = players
    df["position"] = positions
    df["salary"] = salarys
    return df

nba_salary = get_nba_salary()
# print(nba_salary)
# bins 表 共有幾條條狀圖
plt.hist(nba_salary["salary"], bins=15)
plt.show()
```

## 12. pandas 模組作圖--盒鬚圖（box-and-whisker plot）
```python
# NBA 薪水 盒鬚圖（box-and-whisker plot）- 外部的圓圈為離群值
# %matplotlib inline 
import requests
from bs4 import BeautifulSoup
import pandas as pd
import matplotlib.pyplot as plt

def get_nba_salary():
    # chaget to post + payload get morether 100
    payload = {
        "ajax":"true",
        "mobile":"false"
    }
    # r = requests.get("https://www.spotrac.com/nba/rankings/") # only get 100 items
    r = requests.post("https://www.spotrac.com/nba/rankings/", payload)
    # get(text format) parser
    soup = BeautifulSoup(r.text, "html.parser") # parser by html format
    # select process
    salarys = [p.text.replace(",", "") for p in soup.select("td.rank-value span.info")]
    salarys = [int(p.replace("$", "")) for p in salarys]
    players = [p.text for p in soup.select("td.rank-name h3 a")]
    positions =  [p.text for p in soup.select("td.rank-name span.rank-position")]
    # print(salary)
    # print(player)
    # print(position)
    df = pd.DataFrame()
    df["player"] = players
    df["position"] = positions
    df["salary"] = salarys
    return df

nba_salary = get_nba_salary()
#show group count
# grouped = nba_salary.groupby("position").count()
# print(grouped)

# show all position + salary
#for i in range(nba_salary.shape[0]):
#    print('{0:14}-{1:9}'.format(nba_salary.values[i][1], nba_salary.values[i][2]))

# 盒鬚圖（box-and-whisker plot）是資料科學團隊慣常用作探索一組數值資料依類別分組的分佈情況之圖形，
# 藉著圖形可以觀察不同類別分組數值資料的峰度（kurtosis）以及偏態（skewness）
# 資料整理 依行填值
# Return reshaped DataFrame organized by given index / column values
# DataFrame.pivot(index=None, columns=None, values=None)
box_df = nba_salary.pivot(index='player', columns='position', values='salary')
# print(box_df)
# Make a box plot of the DataFrame columns.
box_df.plot.box()
plt.show()
```

## 13. pandas 模組作圖--散佈圖（scatter plot）
```python
# NBA 薪水-得分 散佈圖（scatter plot）
# 因資料的關係,僅有部分球員
%matplotlib inline 
from pyquery import PyQuery as pq
from requests import get
import pandas as pd
import matplotlib.pyplot as plt
import requests
from bs4 import BeautifulSoup
# read json
import json

def get_nba_salary():
    # chaget to post + payload get morether 100
    payload = {
        "ajax":"true",
        "mobile":"false"
    }
    # r = requests.get("https://www.spotrac.com/nba/rankings/") # only get 100 items
    r = requests.post("https://www.spotrac.com/nba/rankings/", payload)
    # get(text format) parser
    soup = BeautifulSoup(r.text, "html.parser") # parser by html format
    # select process
    salarys = [p.text.replace(",", "") for p in soup.select("td.rank-value span.info")]
    salarys = [int(p.replace("$", "")) for p in salarys]
    players = [p.text for p in soup.select("td.rank-name h3 a")]
    positions =  [p.text for p in soup.select("td.rank-name span.rank-position")]
    df = pd.DataFrame()
    df["player"] = players
    df["position"] = positions
    df["salary"] = salarys
    return df

def get_pts_game():
  """
  Get NBA players' PTS/G from NBA.com
  """
  # nba_stats_url = "https://stats.nba.com/stats/leagueLeaders?LeagueID=00&PerMode=PerGame&Scope=S&Season=2017-18&SeasonType=Regular+Season&StatCategory=PTS"
  # pts_game_dict = get(nba_stats_url).json()
  # read json(sometimes get error --> chaneg to read file)
  with open("pts_game.json") as json_file:
    pts_game_dict = json.load(json_file)
  players = [pts_game_dict["resultSet"]["rowSet"][i][2] for i in range(len(pts_game_dict["resultSet"]["rowSet"]))]
  pts_game = [pts_game_dict["resultSet"]["rowSet"][i][22] for i in range(len(pts_game_dict["resultSet"]["rowSet"]))]
  df = pd.DataFrame()
  df["player"] = players
  df["pts_game"] = pts_game
  return df

nba_salary = get_nba_salary()
pts_game = get_pts_game()
df = pd.merge(nba_salary, pts_game)
# matplotlib.pyplot.scatter(x, y, s=None, c=None, marker=None, cmap=None, norm=None, vmin=None, vmax=None, alpha=None,
# linewidths=None, verts=None, edgecolors=None, *, plotnonfinite=False, data=None, **kwargs)
plt.scatter(df["pts_game"], df["salary"])
plt.show()
```

## 14. pandas 模組作圖--線圖（line graph）
```python
# Paul Pierce information - 線圖（line graph）
%matplotlib inline 
from pyquery import PyQuery as pq
import pandas as pd
import matplotlib.pyplot as plt
def get_pp_stats():
  """
  Get Paul Pierce stats from basketball-reference.com
  """
  stats_url = "https://www.basketball-reference.com/players/p/piercpa01.html"
  # pandas direct query url
  html_doc = pq(stats_url)
  # print(html_doc)
  pts_css = "#per_game .full_table .right:nth-child(30)"
  ast_css = "#per_game .full_table .right:nth-child(25)"
  reb_css = "#per_game .full_table .right:nth-child(24)"
  year = [str(i)+"-01-01" for i in range(1999, 2018)]
  # 得分,籃板,助攻
  pts = [float(p.text) for p in html_doc(pts_css)]
  ast = [float(a.text) for a in html_doc(ast_css)]
  reb = [float(r.text) for r in html_doc(reb_css)]
  df = pd.DataFrame()
  df["year"] = year
  df["pts"] = pts
  df["ast"] = ast
  df["reb"] = reb
  return df

pp_stats = get_pp_stats()
# pp_stats["year"] change to datetime mode
pp_stats["year"] = pd.to_datetime(pp_stats["year"] )
# change index to year field
# index 非 datetime 會密密疊在一起
pp_stats = pp_stats.set_index("year")

# draw line graph
# plt.plot(pp_stats["pts"])
# plt.plot(pp_stats["ast"])
# plt.plot(pp_stats["reb"])
# 更改為 line 繪圖
pp_stats.plot.line()
# 放置圖例說明
plt.legend(['PTS', 'REB', 'AST'], loc='upper right')
plt.show()
```

## 15. stock OHLC Candlestick
```python
# K線理論（Candlestick Charts）原意：蠟燭圖；又稱、蠟燭線、日本線、陰陽線、棒線、紅黑線
%matplotlib inline 
import requests
import datetime
import pandas as pd
import chart_studio.plotly as py
import plotly.graph_objs as go

def get_ohlc(twse_ticker):
  """
  Get ohlc data for current month
  """
  today = datetime.datetime.today().strftime('%Y%m%d')
  twse_url = "http://www.twse.com.tw/exchangeReport/STOCK_DAY?response=json&date={}&stockNo={}".format(today, twse_ticker)
  # 未加.json() 僅是 return value 
  stock = requests.get(twse_url).json()
  trading_dates = []
  dates = []
  opens = []
  highs = []
  lows = []
  closes = []
  for i in range(len(stock["data"])):
    trading_dates.append(stock["data"][i][0])
    opens.append(float(stock["data"][i][3]))
    highs.append(float(stock["data"][i][4]))
    lows.append(float(stock["data"][i][5]))
    closes.append(float(stock["data"][i][6]))

  # year 108 --> 2019
  for d in trading_dates:
    sub = d.split("/")
    dates.append("{}-{}-{}".format(int(sub[0])+1911, sub[1], sub[2]))

  df = pd.DataFrame()
  df["trading_date"] = dates
  df["open"] = opens
  df["high"] = highs
  df["low"] = lows
  df["close"] = closes
  df = df.set_index("trading_date")
  return df

tsmc = get_ohlc('2330')
# -- show Candlestick fig --
trace = go.Candlestick(x=tsmc.index,
                       open=tsmc["open"],
                       high=tsmc["high"],
                       low=tsmc["low"],
                       close=tsmc["close"])
# no show bottom fig
layout = go.Layout(
    xaxis = dict(
        rangeslider = dict(
            visible = False
        )
    )
)
fig = go.Figure(data=trace, layout=layout)
fig.show()

# update to plotly wibside(need API key)
py.sign_in('kyp001', 'bEtPpStSQgWRADCmGGe9') # Use your own plotly Username / API Key
py.iplot(fig, filename='simple_candlestick')
```

## 16. 艾姆斯房價（Imes, Iowa）資料分析  
https://www.kaggle.com/c/house-prices-advanced-regression-techniques  
```python
# get % train/test data 
import pandas as pd
from sklearn.model_selection import train_test_split
# ----------------
labeled_url = "https://storage.googleapis.com/kaggle_datasets/House-Prices-Advanced-Regression-Techniques/train.csv"
labeled_df = pd.read_csv(labeled_url)
train_df, validation_df = train_test_split(labeled_df, test_size=0.3, random_state=123)
print(train_df.shape)
print(validation_df.shape)


# 單變數的迴歸模型(相關性)
import pandas as pd
from sklearn.model_selection import train_test_split
# ---------------------
labeled_url = "https://storage.googleapis.com/kaggle_datasets/House-Prices-Advanced-Regression-Techniques/train.csv"
labeled_df = pd.read_csv(labeled_url)
df_corr = labeled_df.corr()
sale_price_corr = df_corr["SalePrice"].abs().sort_values(ascending=False)
print(sale_price_corr)

# GrLivArea(x) vs SalePrice(y)散佈圖（scatter plot）
%matplotlib inline
import pandas as pd
from sklearn.model_selection import train_test_split
import matplotlib.pyplot as plt
# --------------------------
labeled_url = "https://storage.googleapis.com/kaggle_datasets/House-Prices-Advanced-Regression-Techniques/train.csv"
labeled_df = pd.read_csv(labeled_url)
df_corr = labeled_df.corr()
sale_price_corr = df_corr["SalePrice"].abs().sort_values(ascending=False)
plt.scatter(labeled_df["GrLivArea"],labeled_df["SalePrice"])
plt.xlabel('GrLivArea')
plt.ylabel('SalePrice')
plt.show()
```

## 17. read csv then plot  
```python
%matplotlib inline 
import matplotlib.pyplot as plt
import pandas as pd
import warnings
# mask warning -->FutureWarning: Using an implicitly registered datetime converter for a matplotlib plotting method. The converter was registered by pandas on import. Future versions of pandas will require you to explicitly register matplotlib converters.
#To register the converters:
#    >>> from pandas.plotting import register_matplotlib_converters
#    >>> register_matplotlib_converters()
# warnings.warn(msg, FutureWarning)
warnings.filterwarnings("ignore", category=FutureWarning, module="pandas")
# set index by Date
TSMC = pd.read_csv('stock_2330_20190823.csv', index_col='Date')
# change index format to datetime*(so support simple date format for index)
TSMC.index = pd.to_datetime(TSMC.index)
# print(TSMC.Open["2016"])
# print(TSMC)
fig = plt.figure()
plt.plot(TSMC.Open["2016"], '-', label='Open' ,marker=">")
plt.plot(TSMC.Close["2016"], '-', label='Close' ,marker="*")
plt.grid(True, axis='y')
plt.legend()
```
