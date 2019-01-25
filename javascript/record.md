# Javascript record

*   [Root](../README.md)
*	[1. Load Ready](#a1)
*	[2. Get parameter from url string](#a2)
*	[3. String process](#a3)
*	[4. Coding Style check - semistandard](#a4)

<h2 id="a1">1. Load Ready</h2>

```
window.onload = function() {
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

<h2 id="a3">3. String process</h2>

```javascript
// check on string in another string
if (item.Name.indexOf(event.target.value) != -1) {
	return true;
}
else {
	return false;
}

```

<h2 id="a4">4. Coding Style check - semistandard</h2>

*	semistandard

```
1. VSCode install "StandardJS - JavaScript Standard Style"
2. install semistandard
	npm install semistandard -g
3. set VSCode 
	"javascript.validate.enable": false 
4. VSCode 終端機 run 
	semistandard
	--> 若有錯誤,按 ctrl+mouseLeft 就會打開錯誤程式位置
5. 自動修正
	semistandard --fix
6. 增加 issue 說明
	semistandard --verbose
	or
	semistandard -v
```

* other

```
ESLint (通常搭配airbnb 的規範一起使用)
	eslint-plugin-disable (npm module)
	/* eslint-plugin-disable angular, react */
	/* eslint-plugin-disable */
	/* eslint-plugin-disable-all-except angular, react */
	/* eslint-plugin-disable-all-except */
standard (與 ESLint 最大的不同點在於：standard 的規範是死的，所以沒有設定檔，強迫大家都用預設的設定)
```
