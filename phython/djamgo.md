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

python manage.py startapp mainsite

mblog/settings.py
```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'mainsite',
]
LANGUAGE_CODE = 'zh-Hant'
TIME_ZONE = 'Asia/Taipei'
```


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
  slug : 文章網址  

python manage.py makemigrations mainsite  
> 建立DB and Django 間的中介檔案

python manage.py migrate
> 同步更新DB內容  

python manage.py createsuperuser  


* register Post
mainsite/admin.py
```python
from django.contrib import admin
from .models import Post
admin.site.register(Post)
```

http://127.0.0.1:8000/admin/  

* show DB list more field 
```python
class PostAdmin(admin.ModelAdmin):
	list_display = ( 'title', 'slug', 'pub_date')
admin.site.register(Post, PostAdmin)
```

* show app data  
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
mblog/urls.py  
```python
from mainsite.views import homepage
urlpatterns = [
    path('', homepage),
    path('admin/', admin.site.urls),

]
```

http://127.0.0.1:8000/














