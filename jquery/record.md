# jQuery record

* [Root](../README.md)
* [1. sector(選擇器)](#a1)
*	[2. Load Ready](#a2)
*	[3. Control](#a3)

<h2 id="a1">1. sector(選擇器)</h2>

```
$("p.intro")        // p 元素 class==intro
$("p#intro")		// p 元素 id==intro
$("[href]")			// 元素含有屬性 href
$("[href='#']")		// 元素含有屬性 href, href=="#"
$("[href!='#']")       // 元素含有屬性 href, href!="#"
$("[href$='.jpg']")    // 元素含有屬性 href, href值 ".jpg" 結束
$("#title")            // id =="title"
$(".content")          // class=="content"
$("div:has(div)")      // div 有包含 div
$(a[target])           // a 有屬性 target
	
	"div p" - div 內所有的p
	"div>p" - parant為div 的 p
	"div+p" - div 之後的 p
```


<h2 id="a2">2. Load Ready</h2>

```
$(document).ready(function(){
	.....
});

$(function(){
	.....
});
```


<h2 id="a3">3. Control</h2>

>	set HTML value 
```javascript
$("#title").html("進度條");
$("#title")[0].innerHTML = "進度條";
```

>	add class
```javascript
$("div").addClass('special');
```

>	加入文字
```javascript
$(a[target]).append("(Open in New window)")
```

>	id = body 修改 css 屬性
```javascript
$("#body").css("background-color");
$("#body").css({
	border: "1px solid green",
	height: "40px"
});
```
