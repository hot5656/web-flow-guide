# Javascript record

*   [Root](../README.md)
*	[1. Load Ready](#a1)
*	[2. Get parameter from url string](#a2)

<h2 id="a1">1. Load Ready</h2>

```
window.load = function() {
	.......
}
```

<h2 id="a2">2. Get parameter from url string</h2>

```javascript
getParameterString(next, "offset");

// get parameter value 
// no exist resurn null
// http://www.mysite.com/mypage.html?var1=value1&var2=value2&var3=value3
function getParameterString(url, name)
{
     var reg = new RegExp("(^|&)"+ name +"=([^&]*)(&|$)");
     var r = url.substr(1).match(reg);
     if(r!=null)return  unescape(r[2]); return null;
}
```
