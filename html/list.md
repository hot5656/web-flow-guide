# HTML List

*   [Root](../README.md)

### table
```html
<table class="style1">
  <tr>
    <th>標題1</th>
    <th>標題2</th>
  </tr>
  <tr>
    <td>內容1-1</td>
    <td>內容1-2</td>
  </tr>
  <tr>
    <td>內容2-1</td>
    <td>內容2-2</td>
  </tr>
</table>
--> <table> cellspacing="8" : 表格框之寬度
--><table> cellpadding="8" : 表格內容和邊框之距離

//mergin across table
<table width="50%" border="1" cellspacing="5" cellpadding="10">
	<tr>
		<td colspan="2">&nbsp;</td>
		<td rowspan="2">&nbsp;</td>
	</tr>
	<tr>
		<td>&nbsp;</td>
		<td>&nbsp;</td>
	</tr>
</table>
--> colspan="2"
--> rowspan="2"

<table class="table table-dark">
	<thead>
		<tr>
			<th scope="col">#</th>
			<th scope="col">First</th>
			<th scope="col">Last</th>
			<th scope="col">Handle</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<th scope="row">1</th>
			<td>Mark</td>
			<td>Otto</td>
			<td>@mdo</td>
		</tr>
		<tr>
			<th scope="row">2</th>
			<td>Jacob</td>
			<td>Thornton</td>
			<td>@fat</td>
		</tr>
		<tr>
			<th scope="row">3</th>
			<td>Larry</td>
			<td>the Bird</td>
			<td>@twitter</td>
		</tr>
	</tbody>
</table>
scope="col" : 行表頭
scope="row" : 列表頭
<thead>放表格的標題
<tbody>放表格的內容
<tfoot>放表格的註腳
```

### input
```html
<input type="button" class="btn" value="hello">
<input type="button" value="按鍵">
<input type="text" id="mail" placeholder="請輸入電子郵件" name="mail" >

<form action="index.html">
	<label for="mail">電子郵件：</label>
	<input type="text" id="mail" placeholder="請輸入電子郵件" name="mail" >
	<label for="person">姓名：</label>
	<input type="text" id="person" placeholder="請輸入姓名" name="person">
	<br>
	<input type="submit" value="下一步">
</form>

<form action="index.html">
	<h2>性別</h2>
	<input type="radio" name="sex" value="wman"> 男生
	<input type="radio" name="sex" value="woman"> 女生
	<h2>興趣</h2>
	<input type="checkbox" name="hobby" value="movie"> 看電影
	<input type="checkbox" name="hobby" value="music"> 聽音樂
	<input type="checkbox" name="hobby" value="comic"> 看漫畫
	//--- add label for checkbox (間隔會較寬)
	<input type="checkbox" id="check">
	<label for="check">記住我</label>
	<br>
	<input type="submit" value="輸入">
</form>

<form action="index.html">
	<label for="birth"></label>
	<select name="birth" id="birth">
		<option value="1900">1900</option>
		<option value="1901">1901</option>
	</select>
	<h2>內容</h2>
	<textarea name="content" id="" cols="30" rows="10"></textarea>
	<input type="button" value="按鍵">
	<input type="submit" value="輸入">
</form>
```

### select option 下拉式選單

```css
select {
	// 設定無 icon
	appearance: none
	// 更改 icon
  background-image: url("../img/arrows-up-and-down.png")
  background-position: 90% 50% 
  background-repeat: no-repeat
  padding-left: 20px
  height: 56px
  background-color: $c-secondary
  color: $c-info
  margin-bottom: 8px
  border-width: 0
}

<select name="YourLocation">
  // 分類
	<optgroup label="城市"> 
　<option value="Taipei">台北</option>
　<option value="Taoyuan" SELECTED>桃園</option>
　<option value="Hsinchu">新竹</option>
　<option value="Miaoli">苗栗</option>
　...
</select>
```

### other
* 名詞
	*	attribute 屬性
	```
	<a href="https://tw.yahoo.com/"></a>
	href : attribute name
	"https://tw.yahoo.com/" : sttribute value
	// title : show when hover 
	title="test title"
	border="3" border 3px
	bordercolor="#f00"
	width="100"
	height="200"  
	style="..." : put css in html
	```

	* comment
	```html
	<!-- HTML comment -->
	```

*	name (可重複)
	```
	1. 作為可與伺服器交互資料的HTML元素的伺服器端的標示，比如input、select、textarea、和button等。我們可以在伺服器端根據其Name通過Request.Params取得元素送出的值。
	2. HTML元素Input type='radio'分組，我們知道radio button控件在同一個分組類，check操作是mutex的，同一時間只能選中一個radio，這個分組就是根據相同的Name屬性來實現的。
	3. 建立頁面中的錨點，我們知道<a href="URL">link</a>是獲得一個頁面超級連結，如果不用href屬性，而改用Name，如：<a name="PageBottom"></a>，我們就獲得了一個頁面錨點。
	4. ?? 作為對象的Identity，如Applet、Object、Embed等元素。比如在Applet對像實例中，我們將使用其Name來引用該對象
	5. ??  在IMG元素和MAP元素之間關聯的時候，如果要定義IMG的熱點區域，需要使用其屬性usemap，使usemap="#name"(被關聯的MAP元素的Name)。
	6. ?? 某些特定元素的屬性，如attribute，和param。例如為Object定義參數<PARAM NAME = "appletParameter" VALUE = "value">。
	```

*	variable
	```
	let、const是ES6之後加入的新成員，其作用的範圍跟var有些差異
	let與const是區塊作用域(block scope)
	var是函式作用域(function scope)
	因應ES6的出現，使用上建議大家不要再用var來宣告變數，改用let與const，而且優先使用const。
	```

* head
	```
	// title
	<title>webpage Home</title> : browser tab
	// link
	<link rel="stylesheet" href="style.css"> : inclue css file
	// icon : at top of title(px 為四的倍數 16*16 or 64*64)
	<link rel="shortcut icon" type="image/x-icon" href="/somewhere/myicon.ico">
	<link rel="shortcut icon" type="image/gif" href="/somewhere/myicon.gif">
	<link rel="shortcut icon" type="image/png" href="/somewhere/myicon.png">
		--> 	<link rel="shortcut icon" type="image/x-icon" href="favicon_32.ico">
		--> 	<link rel="icon" type="image/x-icon" href="favicon_32.ico">
	// javascript file 
	<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
	// javascript code
	<script>
		............
	</script>
	// css code
	<style> : head
		............
	</style>
	// <meta/> : tags  when write keyword to describe your webside
		// 說明,不要太長
		<meta name="description" cntent="this is descript the side" />
		// keyword
		<meta name="keywords" content="learn, httml, html5, css, css3" />
		// refresh page(this is every 5s)
		<meta http-equiv="refresh" content="5">
		// redirect to another page		
		<meta http-equiv="refresh" content="0;URL=index.html">
	```
* element
	*	page name
	```
	banner : 旗幟,橫幅
	```

	* list
	```html
	// unorder list
	<ul>
		<li>First item</li>
		<li>Second item</li>
		<li>third item</li>
	</ul>
	// <ul> type
			type="square"
			type="disk"(default)
			type="circle"
			type="none"
	// order list
	<ol>
		<li>First item</li>
		<li>Second item</li>
		<li>third item</li>		
	</ol>
	// <ol> type
		type="1"(default) --> start="3"
		type="a"
		type="A"
		type="i"
		type="I"
	//  <ol> start
		just support start="3","4"...
	// difinition list定義
	<dl>
		<dt>Title</dt>
			<dd>Definition goes in here</dd>
		<dt>Second title</dt>
			<dd>Another definition</dd>
	</dl>
	// tag
	<dl> = definition list
	<dt> = definition Title
	<dd> = definition Descript
	// show as
	Title
			Definition goes in here
	Second title
			Another definition
	```

	*	cookie
	```
	// Cookie 技術是在瀏覽器儲存資訊的一種方法， 而這些資訊就稱為 Cookie ， 伺服器可以儲存一些資訊到瀏覽器， 到下次瀏覽器再與伺服器溝通時， 這時資訊就會傳到伺服器
	// Cookies are primarily for server-side reading (can also be read on client-side), localStorage and sessionStorage can only be read on client-side.
	// Size must be less than 4KB.
	// Cookies can be made secure by setting the httpOnly flag as true for that cookie. This prevents client-side access to that cookie
	```

	* other
	```html
	// head
		<h1></h1>~<h6></h6>
	// img
		<<img src="" alt="">
		alt: if cannot load show message
	// bold
		<b></b> : for browser
		<strong></strong> : for more screen
	// Italic
		<em></em> : for emphasize 強調
		<i></i> : fo decoration 裝飾
	// under line
		<u></u>
	// button
		<button type="button">我是按鈕</button>
	// sub text
		<sub>xx</sub> : low word
	// super text
		<sup></sup> : high word
	// code text
		<code>show computer code</code> : show speial font for code
	// pre text(preformat, block element) : shwo as input, don't need <br> (incluse new line, space...)
		<pre>My pre
		Starts    sss
		end Per</pre>
	// font tag : 有調整 color ,size, face 的 attribute
		<font color="顏色" size="大小" face="字型">文字</font>
	// IFrames : inline frame
		<iframe src="https://hot5656.github.io/dessertshop_susy/" frameborder="1" height="400px" width="50%" scrolling="yes"></iframe>
		--> frameborder="0" or "1"(have border)
		--> some web sise not support
		--> support width and height
		--> scrolling
			scrolling="yes" scroll bar always show up
			scrolling="no"  scroll bar never show up
			scrolling="auto" scroll bar auto detect show up or not
	// tag a(link tag or anchor)
		<a href="index.html" class="next">繼續逛逛</a>
		<a class="pay" href="checkout_profile.html">結帳</a>
		attribute target :
			_blank  : Opens the linked document in a new window or tab
			_self   : (defalut)Opens the linked document in the same frame as it was clicked
			_parent : Opens the linked document in the parent frame
			_top    : Opens the linked document in the full body of the window
			framename	: Opens the linked document in a named frame
		href="#" : goto page top
		href="#page-middle" : got page position id = page-middle
	// div
		<div></div> : dummy element, no real function
	// icon 語法
		.ico語法1：
		<link rel="shortcut icon" href="圖示網址/favicon.ico" />
		.ico語法2：
		<link rel="icon" href="圖示網址/favicon.ico" type="image/ico" />
	// br - break line
		<br>
	// hr - 分隔線
		<hr>
	// a link but no do anything
		<a href="javascript: void(0)">Link</a>
	// <b>: bold
		<b></b>
	```

### DOM(Document Object Model Tree)
*	HTML element
	```
	<html>-<head>-<title>-text
							 -<meta>
				-<body>-<h1></h1>-text
							 -<img>
							 -<p>-text
							 		 -<em>
	```

* show HTML entify
	```
	<div><meta/>tags go in your <head>section</div>
		to
	<div>&lt;meta/&gt;tags go in your &lt;head&gt;section</div>	
	```

### HTML5
* video element
	```
	// chrome 要設定 muted, autoplay才有作用
	// post : 影片撥放錢顯示圖片
	// muted/muted="true" : 靜音
	// autoplay/autoplay="autoplay" : 網頁載入後自動撥放 (若有問題可加 preload)
	// controls/controls="controls" : 顯示控制鍵
	// loop/loop="loop" : 重複播放
	// width="200"/height="300": 設定寬度/高度
	<video autoplay poster="photo-1473256599800-b48c7c88cd7e.jpg"  muted >
			<source src="Christmas - 19940.mp4" type="video/mp4">
			<!-- if browser not support shoe the text -->
			Your browser don't suppoer the video tag.
	</video>
	<video autoplay muted loop>
			<source src="SampleVideo_720x480_1mb.mp4" type="video/mp4" >
			Your browser don't suppoer the video tag.
	</video>
	// 另外也有其他撥放檔
	<video>
		<source src="SampleVideo_720x480_1mb.mp4" type="video/mp4" >
		<source src="SampleVideo_720x480_1mb.ogg" type="video/ogg" >
		<source src="SampleVideo_720x480_1mb.webm" type="video/wem" >
		Your browser don't suppoer the video tag.
	</video>
	// button + js conttrol video
	// html
	<button onclick="playOrPause()">Play or Pause</button>
	<button onclick="bigScreen()">Big screen</button>
	<button onclick="normalScreen()">Normal screen</button>
	<br>
	<video id="lecture">
			<source src="SampleVideo_720x480_1mb.mp4" type="video/mp4" >
			Your browser don't suppoer the video tag.
	</video>	
	// js
	<script>
		var lecture = document.getElementById("lecture");
		function playOrPause(){
			if (lecture.paused) {
				lecture.play();
			}
			else {
				lecture.pause();
			}
		}
		function bigScreen(){
			lecture.width = 1000 ;
		}
		function normalScreen(){
			lecture.width = 720 ;
		}
	</script>
	```

* audio element
	```
	// muted/muted="true" : 靜音
	// controls/controls="controls" : 顯示控制鍵
	// loop/loop="loop" : 重複播放
	<audio controls>
		<source src="Monplaisir_-_01_-_Hlice.mp3" type="audio/mpeg">
		Your browser don't support the audio tag
	</audio>
	// 另外也有其他撥放檔
	<audio controls>
		<source src="Monplaisir_-_01_-_Hlice.mp3" type="audio/mpeg">
		<source src="Monplaisir_-_01_-_Hlice.ogg" type="audio/ogg">
		<source src="Monplaisir_-_01_-_Hlice.wav" type="audio/wav">
		Your browser don't support the audio tag
	</audio>
	```

* drag an drop  
	[good reference](https://pjchender.blogspot.com/2017/08/html5-drag-and-drop-api.html)
	* simple 

	```css
	// css
	/*預防選到 drag source 內部內容 */ 
	[draggable="true"] {
	  user-select: none;
	  -moz-user-select: none;
	  -webkit-user-select: none;
	  -ms-user-select: none;
	}
	#source-container, #target-container{
		display: inline-block;
		margin: 10px;
		border-width: 1px;
		height: 200px;
		width: 45%;
		background-color: pink;
	}
	#drag-source {
		width: 100px;
		height: 100px;
		background-color: blue;
		border-radius: 50%
	}
	// html
	<div id="source-container">
		<!-- drag source set draggable="true" -->
		<div id="drag-source" draggable="true" ondragstart="dragStart(event)"></div>
	</div>
	<div id="target-container" ondrop="dropped(event)" ondragover="cancelDefault(event)" ondragenter="cancelDefault(event)"></div>
	// js
	// monitor dragover and dragenter not do default 
	// jQuery 的 event handler 最後加上 return false 來得到 preventDefault() 與 stopPropagation() 的效果
  // JavaScript 的 addEventListener() 裡，最後面加上 return false 只會有 preventDefault() 的效果，不會有 stopPropagation() 的作用。
	function cancelDefault(e) {
		// 終止預設行為(Stop Event Flow)
		// 以「超連結」為例，瀏覽器看到頁面上有超連結，只要偵測到超連結被點擊到，隨即會幫我做「導向連結」的動作，「導向連結」即是超連結的預設行為
		e.preventDefault();
		//終止事件傳導 : 停止傳送trigger至父層
		e.stopPropagation();
		return false;
	}

	// monitor dragstart setData for traget 
	function dragStart(e) {
		console.log("dragStart");
		e.dataTransfer.setData('text/plain', e.target.id);
	}
	
	// monitor drop and getData(need remove default trigger)
	function dropped(e) {
		console.log("dropped");
		cancelDefault(e);
		let data = e.dataTransfer.getData('text/plain');
		e.target.appendChild(document.getElementById(data));
	}
	```

	* drag and drop 2  block

	```css
	// css
	/*預防選到 drag source 內部內容 */ 
	[draggable="true"] {
	  user-select: none;
	  -moz-user-select: none;
	  -webkit-user-select: none;
	  -ms-user-select: none;
	}
	#source-container, #target-container{
		display: inline-block;
		margin: 10px;
		border-width: 1px;
		height: 200px;
		width: 45%;
		border: 1px solid #000;
	}
	#drag-source {
		width: 100px;
		height: 100px;
		background-color: blue;
		border-radius: 50%
	}
	// html
	<!-- add data-role="drag-drop-container" for two direct -->
	<div id="source-container" data-role="drag-drop-container" >
		<div id="drag-source" draggable="true"></div>
	</div>
	<div id="target-container" data-role="drag-drop-container"></div>
	// js
	// set multi draggable listen 
	let dragSource = document.querySelectorAll('[draggable="true"]');
	dragSource.forEach(function(element){
			element.addEventListener('dragstart', dragStart);
	}); 
	// set multi drop target listen 
	let dropTaret = document.querySelectorAll('[data-role="drag-drop-container"]');
	dropTaret.forEach(function(element){
		element.addEventListener('drop', dropped);
		element.addEventListener('dragenter', cancelDefault);
		element.addEventListener('dragover', cancelDefault);
	});

	// monitor dragover and dragenter not do default trigger
	function cancelDefault(e) {
		// 終止預設行為(Stop Event Flow)
		// 以「超連結」為例，瀏覽器看到頁面上有超連結，只要偵測到超連結被點擊到，隨即會幫我做「導向連結」的動作，「導向連結」即是超連結的預設行為
		e.preventDefault();
		//終止事件傳導 : 停止傳送trigger至父層
		e.stopPropagation();
		return false;
	}

	// monitor dragstart setData for traget 
	function dragStart(e) {
		console.log("dragStart");
		e.dataTransfer.setData('text/plain', e.target.id);
	}
	
	// monitor drop and getData(need remove default trigger)
	function dropped(e) {
		console.log("dropped");
		cancelDefault(e);
		let data = e.dataTransfer.getData('text/plain');
		e.target.appendChild(document.getElementById(data));
	}
	```

	* drop change elemnt and other
	```
	// css
	// For drag sources
	.dragging {
	  opacity: .25;
	}

	// For drop target
	.hover {
	  background-color: rgba(0,191,165,.04);
	}
	// js - drag source
	// 針對物件本身，我們在開始拖曳時添加樣式，結束拖曳時移除樣式：
	function dragStart (e) {
	  this.classList.add('dragging')
	  e.dataTransfer.setData('text/plain', e.target.id)
	}

	function dragEnd (e) {
	  this.classList.remove('dragging')
	}
	// js - container
	// 針對容器，我們在進入容器時添加樣式，在離開或放置後移除樣式：
	function dropped (e) {
	  let id = e.dataTransfer.getData('text/plain')
	  e.target.appendChild(document.querySelector('#' + id))
	  this.classList.remove('hover')
	}

	function dragOver (e) {
	  this.classList.add('hover')
	}

	function dragLeave (e) {
	  this.classList.remove('hover')
	}	
	```

	*	drag drop llist(include jQuery)

	```
	// include jQuery
	<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
	// html
	<ul id="item-list" class="moveable">
		<li>One</li>
		<li>Two</li>
		<li>Three</li>
		<li>Four</li>
	</ul>
	// js+jQuery
	$(document).ready(function(){
		let items = document.querySelectorAll('#item-list > li');
		items.forEach(item => {
			item.setAttribute("draggable", "true");
			item.addEventListener('dragstart', dragStart);
			item.addEventListener('drop', dropped);
			item.addEventListener('dragenter', cancelDefault);
			item.addEventListener('dragover', cancelDefault);
		});
		// monitor dragover and dragenter not do default trigger
		function cancelDefault(e) {
			e.preventDefault();
			e.stopPropagation();
			return false;
		}

		// monitor dragstart setData for traget 
		function dragStart(e) {
			let index = $(e.target).index();
			console.log("dragStart");
			console.log("index="+index);
			e.dataTransfer.setData('text/plain', index);
		}
		
		// monitor drop and getData(need remove default trigger)
		function dropped(e) {
			console.log("dropped");
			cancelDefault(e);
			
			let oldIndex = e.dataTransfer.getData('text/plain');
			let target = $(e.target);
			let newIndex = target.index();

			// remove dropped item at old place
			let dropped = $(this).parent().children().eq(oldIndex).remove();

			// insert the dropped items at new place
			if (newIndex < oldIndex) {
				target.before(dropped);
			}
			else {
				target.after(dropped);
			}
		}
	});
	```

* Navigator Geolocation(user location)  
	[Navigator API](https://developer.mozilla.org/en-US/docs/Web/API/Navigator)  
	[getCurrentPosition() Method](https://www.w3schools.com/html/html5_geolocation.asp)
	```
	// GeoLocation API 可以讓您知道使用者所在，但一律要獲得使用者同意
	// html 
	<p id="coords"></p>
	<button onclick="getMyposition()"> find me!</button>
	// js
	var myLoc = document.getElementById("coords");
	function getMyposition() {
		if (navigator.geolocation) {
			navigator.geolocation.getCurrentPosition(showPosition);
		}
		else {
			myLoc.innerHTML = "Geolocation isn't supported by this browser.";
		}
	}
	function showPosition(position) {
		//緯度(latitude),經度(longitude),座標(coords-coordinates)
		myLoc.innerHTML = "Latitude : "+ position.coords.latitude +
											"<br>Longitude : " + position.coords.longitude;
	}
	```

* localStorange(Saving Information)
	```
	// 儲存在 localStorage 的資料，關閉瀏覽器依舊會存在
	// 儲存在 sessionStorage 的資料，在關閉瀏覽器後，就不見了
	// set 
	localStorage["test1"]='a'; //儲存資料，方法1
	localStorage.test2='b'; //儲存資料，方法2
	localStorage.setItem("test3","c"); //儲存資料，方法3
	// get
	alert(localStorage["test1"]); //讀取資料，方法1
	alert(localStorage.test2); //讀取資料，方法2
	alert(localStorage.getItem("test3")); //讀取資料，方法3
	// remove
	localStorage.removeItem("test1"); //刪除key值為test1這筆資料
	localStorage.clear(); //刪除localStorage裡所有資料
	// 若想將整個 Storage 從瀏覽器刪除可以使用 removeItem() 方法，或是直接手動清除瀏覽器中的 cache。
	// html
	<p id="coords"></p>
	<button onclick="getMyposition()"> find me!</button>
	// check Storage support or not
	if(typeof(Storage)!=="undefined") {
		// accept
		alert("Accepted");
	}
	else {
		// not accept
		alert("No local Storage accepted");
	}
	// save variable to localStorange
	localStorage.myName = "Robert Kao";
	localStorage.Son = "Little Robert";
	alert(localStorage.myName);
	```

* sessionStorange(Saving Information)
	```
	// html
	<button type button="button" onclick="counter()">Add one!</button>
	<div id="number"></div>
	// js 
	function counter() {
		if(typeof(Storage)!=="undefined") {
			if (sessionStorage.counter) {
				sessionStorage.counter = Number(sessionStorage.counter) + 1;
			}
			else {
				sessionStorage.counter = 1;
			}
			document.getElementById("number").innerHTML = sessionStorage.counter;
			if (sessionStorage.counter>1) {
				document.getElementById("number").innerHTML += "<p>Reference the page</p>" ;
			}
		}
		else {
			document.getElementById("number").innerHTML = "The browser doesn't support webv storage";
		}
	}
	```

* addition element
	```
	// new element
	<header></header> : per page support multi, but not inside
	<footer></footer> : per page support multi, but not inside
	<nav></nav> : navigation 
	<area shape="" coords="" href="" alt=""> : general for group
	<article></article> : an artical
	<section></section> : a section of content goes, linke code, artical, etc
	// spellcheck and contenteditable - applied by <p>,<body>,<div>...
	// some element need add  contenteditable="true" the ncan do spellcheck
	<p contenteditable="true" spellcheck="true">splel chekc tihs sentance</p>
	// video 
	```



