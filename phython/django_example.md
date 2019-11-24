## [Python Guide](./python_guide.md)

## Django Example

* add no input string except  
```python
# user_id, user_pass, user_post no input trigger except
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
```

* add DB record  
```python
if user_id != None :
	mood = Mood.objects.get(status=user_mood)
	post = Post.objects.create( 
		mood = mood,
		nickname = user_id,
		del_pass = user_pass,
		message = user_post
		)
	post.save()
```

* get DB filter  
max 4 record(0~3)  
```python
posts = Post.objects.filter(enable=True).order_by('-pub_time')[:4]
```

* year 下拉式選單  
	views  
	```python
	# year select
	year = range(1956,2020)
	```

	html  
	```html
	<!-- year select -->
	<label for="byear">出生年:</label>
	<select name="byear" id="byear">
		{% for y in year %}
			<option value="{{ y }}">{{ y }}</option>
		{% endfor %}
	</select>
	```

* checkbox process  
	views  
	```python
	# get checkbox 
	urfcolor = request.GET.getlist('cfcolor')
	```

	html  
	```html
	顏色喜好 : 
	<!-- get checkbox --> 
	{% for c in urfcolor %}
		{{ c }}
	{% empty %}
		not selected
	{% endfor %}
	```

* include local js  
```html
{% load static %}
<!-- local js -->
<script src="{% static 'js/all.js' %}"></script>
```

* load local image  
```html
{% load static %}
<img src="{% static 'images/flower.jpg' %}" alt="" height="64" width="64">
```

* Redirection  
```python
# Redirection 
# from django.http import HttpResponseRedirect
from django.shortcuts import redirect
# Redirection 
# return HttpResponseRedirect(reverse('list/')) - not work
return redirect('/list/')
```
