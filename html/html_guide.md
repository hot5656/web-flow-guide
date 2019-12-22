# HTML Guide  

[Javascript example](./js_example.md)  
[Css example](./css_example.md)  
[Tag](#tag)  
[css](#css)  
[Javascript](#javascript)  
[Other](#other)  
[Reference link](#ref_link)  

<a id="tag"></a>
## Tag  [[Home]](#)  
```html
<!-- ... --> : 註解
<h1></h1>~<h6></h6>
<p></p>
<a href=""></a>
<img src="flower.jpg" alt="flower">

figure :代表一段獨立的内容(是圖像，插圖，圖表，代碼片段等)
figcaption : 說明
<figure>
	<img src="pic/flower.jpg" alt="flower">
	<figcaption>
	花...
	</figcaption>
</figure>

<ul> : unorder list
	<li>清單</li>
	<li>清單</li>
</ul>

<ol> : order list
	<li>步驟一</li>
	<li>步驟二</li>
</ol>

<nav> : 導覽頁
	<a href="">選單</a>
	<a href="">選單</a>
	<a href="">選單</a>
</nav>

// table 
<table border='2'>
	<tr>
		<td>data</td>
		<td>data</td>
		<td>data</td>
		<td>data</td>
		<td>data</td>
	</tr>
	<tr>
		<td>data</td>
		<td>data</td>
		<td>data</td>
		<td>data</td>
		<td>data</td>
	</tr>
</table>

<strong></strong> : 強調(粗體)
<em></em> : 強調(斜體)
<b></b> : 粗體
<i></i> : 斜體
<style> : html set ccs
	......
</style>
```

<a id="css"></a>
## css  [[Home]](#)  
階層式樣式表(Cascading Style Sheets)  
*	in HTML  
```html
<!DOCTYPE html>
<html lang="en">
<head>
	....
	<title>Document</title>
	<link rel="stylesheet" href="style.css">
	<style>
		p {
			color: red;
			background: gray;
			font-size: 20px;
		}
	</style>
</head>
<body>
	<!-- inline style -->
	<p style="color:red;">...</p>
</body>
</html>
```

* 註解  
```
/* .... */ 
```

* type  
```
p {
	....
}
.class {
	....
}
＊ {
	....
}
```

* css items 
```css
	margin: 0;
	margin-bottom: 30px;
	padding: 0;
	color: #fa0;
	font-size: 60px;
	text-align: center; - 文字位置
	text-decoration: none; - 文字修飾(無底線,刪除)
	display: inline-block; 
	padding: 6px 20px;
	// css3
	transition: 1s; - 轉換速率
	```


<a id="javascript"></a>
## Javascript  [[Home]](#)  

* debug  
	* console.log  
	```js
	console.log("myFunction")
	```

* Web APIs 
	* windows  
	```js
	// 頁面跳轉
	var usr = '/' + id + '/' + user_pass;
	window.location = usr;
	```

<a id="other"></a>
## Other[[Home]](#)  
* lorem  
```html
lorem
```

* color  
	* RGB color  
	RGB色彩在網頁設計時的標記方式是 RGB(0-255 , 0-255, 0-255)，其中括弧內以逗號分隔的三組數值恰好就是 (R, G, B) 的色彩數值  
	RGB色彩以R在上方順時針排列，而中間產出的混合色採則是我們印表機的C、M、Y(藍、洋紅、黃)三色
	![RGB-color](RGB-color.png)

	* HSL color  
	HSL(Hue, Saturation, Lightness)色彩寫法，HSL色彩的寫法是 HSL(色相角度但不加單位0-360, 色彩飽和度0-100%, 色彩亮度0-100%)，而在括號內的色相採用的是0-360度，正常所見的語法就像是這樣  
		* 色相 （Hue）  
		色相的0度為R(紅)色，120度為G（綠）色，240度為B（藍）  
		![HSL-color](HSL-color.png)
		* 飽和度（Saturation）- 鮮豔   
		![HSL-color-Saturation](HSL-color-Saturation.png)
		* 亮度/明度（Lightness）  
		![HSL-color-Lightness](HSL-color-Lightness.png)

	* 調整  
	需要先將原色設定出來，接著再利用第三色來調整亮度，這樣就搞定了！那若是我們想要調暗的話，那就是把原本的兩個色彩數值降低(也就是光線強度開若一點的概念)，這樣就你就可以把顏色設定出來囉  

* SEO:搜尋引擎最佳化  
搜尋引擎優化 (SEO) : 透過自然排序（無付費）的方式增加網頁能見度的行銷規律。SEO包含技術與創意，用以提高網頁排名、流量，以及增加網頁在搜尋引擎的曝光度。  

* attribute(屬性) 
```html
src : attribute
<img src="flower.jpg" alt="flower">
style : set attribute  
<p style="color:red;">...</p>
```

* 名詞  
	* inline style  
	```html
	<p style="color:red;">...</p>
	```

	* XMind: ZEN(心智圖)  
	* Evernote
	* Notion
	* OneNote 


<a id="ref_link"></a>
## Reference link  [[Home]](#)  
* [w3schools](https://www.w3schools.com/)  
* [MDN](https://developer.mozilla.org/zh-TW/)  
* [W3C](https://www.w3.org/)  
* [CODEPEN](https://codepen.io/)  
* [網頁色彩碼](http://csscoke.com/2015/01/01/rgb-hsl-hex/)  
* [網頁色彩表](https://www.ifreesite.com/color/)  
* [假圖 Fake images please](https://fakeimg.pl/)  
* [假圖 picsum](https://picsum.photos/)  
* [Can I use](https://caniuse.com/)  
* [Emmet doc](https://docs.emmet.io/cheat-sheet/)  
* [排版設計](http://brandingdesign.nccu.tilda.ws/newbiebecomeeilte/layout)  
* [Free Website Templates(版型)](https://freewebsitetemplates.com/)  
* [版型](https://templated.co/)-[reff](https://www.minwt.com/webdesign-dev/html/11814.html)  
* [製作基本版型](http://epaper.gotop.com.tw/PDFSample/AEL019700.pdf)  
* [HTML5 Structural Elements](https://www.dwuser.com/education/content/an-introduction-to-the-html5-structural-elements/)  
* [裝置解析度查詢](http://csscoke.com/webq/index.html)  
* [Bootstrap](https://getbootstrap.com/)  
* [jQuery](https://jquery.com/)  
* [Google Hosted Libraries](https://developers.google.com/speed/libraries)  
* [Google Fonts](https://fonts.google.com/)  


