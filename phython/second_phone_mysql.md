django-admin startproject sellphoneqsl
cd sellphoneqsl
python manage.py startapp secondphone


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
TIME_ZONE = 'Asia/Taipei

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
DATA_UPLOAD_MAX_NUMBER_FIELDS = 1000

* install mysqlclient  
conda install mysqlclient

* check set up
python manage.py check

* models.py
```
class Maker(models.Model):
	name = models.CharField(max_length=10)
	country = models.CharField(max_length=10)

	def __str__(self):
		return self.name
```

* register models
admin.py
```
from django.contrib import admin
from .models import Maker
# --- admin cannot see ---
# admin.site.register(Maker)
# --- admin work well ---
class MakerAdmin(admin.ModelAdmin):
  list_display = ( 'name', 'country')
admin.site.register(Maker, MakerAdmin)
```

python manage.py makemigrations
python manage.py migrate

create supersure then run server
python manage.py createsuperuser
python manage.py runserver

http://127.0.0.1:8000
http://127.0.0.1:8000/admin/


* add other DB  

* models.py
```
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
	make = models.ForeignKey(PModel, on_delete=models.CASCADE) 
	nickname = models.CharField(max_length=15, default='超級二手機')
	description = models.TextField(default='暫無說明')
	year = models.PositiveIntegerField(default=2016)
	price = models.PositiveIntegerField(default=0)

	def __str__(self):
		return self.nickname

class PPhoto(models.Model):
	product = models.ForeignKey(Product, on_delete=models.CASCADE) 
	description = models.CharField(max_length=20, default="產品照片")
	url = models.URLField(default='https://i5.walmartimages.com/asr/e82d7b52-8231-4ae8-8265-4e51fa26c5a1_2.09e8f3ddc9ef442cdeffb2f5485ada64.png?odnWidth=450&odnHeight=450&odnBg=ffffff')

	def __str__(self):
		return self.description
```

admin.py
```
from django.contrib import admin

from .models import Maker
from .models import PModel
from .models import Product
from .models import PPhoto
#admin.site.register(Maker)

class MakerAdmin(admin.ModelAdmin):
  list_display = ( 'name', 'country')
admin.site.register(Maker, MakerAdmin)

admin.site.register(PModel)
admin.site.register(Product)
admin.site.register(PPhoto)
```


* system urls 

* app urls 

* VS code set for Django

```python
{
  "emmet.includeLanguages": {"django-html": "html"},
  "python.linting.pylintArgs": [
      "--load-plugins=pylint_django"
  ],
}
```

* templates
templates/second

