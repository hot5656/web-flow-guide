# Javascript List

*   [Root](../README.md)
*   [JavaScript 基礎](https://developer.mozilla.org/zh-TW/docs/Learn/Getting_started_with_the_web/JavaScript_basics)
*   [w3schools JavaScript](https://www.w3schools.com/js/default.asp)
*   [jsbin - onlie run js JavaScript](https://jsbin.com/?html,output)
*   [MDN(Mozilla Developer Cente) chinese string](https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Reference/Global_Objects/String)
*   [DOM spec](https://dom.spec.whatwg.org/)




### basic
*	HTML inline
```javascript
	// button direct call
	<button onclick="alert('hello')">Press</button>
```


*	html include js - < script > ... </ script >
	```javascript
	<!DOCTYPE html>
	<html lang="en">
	<head>
		<meta charset="UTF-8">
		<title>Document</title>
		<!-- 	<script>
			alert("test");
		</script> -->
	</head>
	<body>
		<h1>Title</h1>
		<!-- js script -->
		<script>
			alert("test");
		</script>
	</body>
	</html>
	```
*	load js from html
	```javascript
	<script src="scripts/main.js"></script>
	```
* varibale
	```javascript
	var age;			// undefined
	var age2=null // set to empty
	age = 40;
	var counter = 20;
	var isSunnyday = true;
	// --------------------
	/* variable type
		String : \',\\,\",\t,\n,"David "+ "Wang"
		Number : 1, 2.34
		Boolean : true, false, isSunday
		Array
		Object
	*/
	var myVariable = 'Bob';
	var myVariable = 10;
	var myVariable = true;
	var myVariable = [1,'Bob','Steve',10];
	// 呼叫陣列的每一個成員：myVariable[0]、myVariable[1]
	var myVariable = document.querySelector('h1');
	// 基本上，JavaScript 內的所有東西都可以視為一個物件
	// ----------------
	// variable value copy
	var firstName = "John";
	var referenceToName = firstName; 
	firstName = "Joe";
		--> referenceToName
				Joe
	// variable reference copy
	var user = {firestName: "John", LastName="Doe"};
	var refernceToUser = user;
	user.firstName = "Joe"
		--> refernceToUser
			firestName: "Joe"
			LastName="Doe"
	```
* string
	```
	// function for string
		var sentence = "This is sentence";
		sentence.length
		sentence.toUpperCase()
		sentence.toLowerCase()
		sentence.charAt(0)
		sentence.charAt(3)
		sentence.charAt(sentence.length-1)
	// -- add str and number
		"abc " + number + " end"
	// split string to array
		var myString = "The quick brown fox jumps over th laxy dog";
		var arrayString = myString.split(" ");
	// substr
		myString.substr(0,7) - from position 0 ,7 char
		myString.substr(7) - from position 7 to end
	```
* Math 
	```
	Math.pow(x, y) - x y 次方
	Math.random() - random 0 to 1 (not include 1)

	Math.PI: 3.14159.

	Math.round(): 四捨五入
	Math.floor(x) - 轉成整數,無條件捨去
	Math.round(x) - 轉成整數,無條件進入
	Math.ceil(): 無條件進位
	Math.min(1,5 ,8)
	Math.nax(55,10,90)

	sin(x)
	cos(x)
	tan(x)
	log(x): log base e
	sqrt(x): square
	```

* color 
	```
	rgba(a,b,c,d) : d - 透明度 1:不透明
	```

* arrays and implicit iteration
	```javascript
	// define
	var myArray = new Array();
	var myArray = new Array("a1","a2", "a3");
	var myArray = [];
	var myArray = [["Bill","David","Mary"],[22, 32, 40]];
	var webCategories = ["Front End Developer", "Background Developer", "Fullstack Developer"];
	var myObject = {
		name: "David"
	};
	var numberValue = 10;
	var mixedArray = [numberValue, "I'm a string", true, myObject];
	// array length
	mixedArray.length
	// set centain item - not set item "undefined"
	myArray[10] = " test string"
	// link 2 array - just link, must set to another array
	webCategories.concat(mixedArray);
	// add new element
	mixedArray.push("another string");
	// remove last element
	mixedArray.pop();
	//remove 1st element
	mixedArray.shift();
	// remove range array - remove from position 1 , 1 item
	// just return result, not change array
	mixedArray.splice(1,1);
	--> add item : mixedArray.splice(1,0,"embedded"); - add item at position 1
	// ------------------------
	// implicit iteration
	var uppercaseCategories = [];
	//                        --> source element
	//                                        --> source array
	function uppercaseElement(element, index, array) {
        uppercaseCategories.push( element.toUpperCase())
		console.log(element);
		console.log(index);
		console.log(array);
	}
	// call ...
	// --> source array
	//                   --> function
	webCategories.forEach(uppercaseElement);
	// ---------------------
	// explicit iteration
	var webCategories = ["Front End Developer", "Background Developer", "Fullstack Developer"];
	var uppercaseCategories = [];
	webCategories[4] = "last element";
	for (i=0 ; i<webCategories.length ; i++ ) {
		if ( webCategories[i] !== undefined) {
			// string start "last"
			if (webCategories[i].indexOf("last") === 0) {
				break;
			}
			uppercaseCategories.push(webCategories[i].toUpperCase());
		}
	}
	``` 
* object
	* normal
	```
	var object;
	object = {
		name: "Mickey",
		lastName: "Mouse",
		age: 40,
		getFullName: function() {
			return "Mickey Mouse";
		}
	};
	object.name
	object.age=60;
	object.getFullName();
	// -----------
	var usetr;
	user = {	
		login: "",
		password: "",
		firstName: "",
		lastName: "",
		"full name": "",
		getFullName: function() {
			return this.firstName+ " " + this.lastName;
		}
	};
	user["login"]
	user["full name"]
	--> var propertyToAccess = "firstName";
	    user.propertyToAccess
	    user[propertyToAccess]
	```
	* another way create object
	```
	// function for object
	function Car() {
		this.namberOfDoors = 4;
		this.brand = "Nissan";
	}
	// create object
	var myNewCard = new Car();
		--> myNewCard
			namberOfDoors: 4;
			brand: "Nissan"
	// check myNewCard's construtor
	myNewCard.construtor 
		Car() {
			this.namberOfDoors = 4;
			this.brand = "Nissan";
		}
	// -------------
	// add parameter input
	function Car(numberDoors, brand) {
		this.namberOfDoors = numberDoors;
		this.brand = brand;
	}	
	// create object
	var myNewCard = new Car(5, "Toyota");	
		--> myNewCard
			namberOfDoors: 5
			brand: "Toyota"	
	// create other 
	var luxuryCard = new Car(2, "luxury");	
	var ludicrousCar = new Car(0, "ludicrous");	
	```
* global variable
	```javascript
	// normal use
		window.innerWidth: 視窗寬度 
		window.innerHeight: 視窗高度
				or 
		// document.documentElement - root element of the document
		document.documentElement.clientWidth: 視窗寬度(can use not include padding,margin,scoll...)
		document.documentElement.clientHeight:  視窗高度
	// event variable
		event.clientX): mouse X
		event.clientX): mouse Y
	// other
		// window.location - 導向網頁
		window.location = "https://shopping.pchome.com.tw/" ;
	```
* function
	* define
	```javascript
	function fun_name(para1, para2) {
		....
		return;
	}
	// simple
	(para1, para2) => {}
	//--------------------
	// variable for function
	var referenceToFun = fun_name() ;
		--> run referenceToFun()
	// ----------------
	// function protype
	function Car() {
		this.namberOfDoors = 4;
		this.brand = "Nissan";
	}
	var luxuryCar = new Car();
	var cheapCar = new Car();
  // add property var for Car - give default 
	Car.prototype.author = "David";
	// add function 
	function Car() {
		this.namberOfDoors = 4;
		this.brand = "Nissan";
		// 每次 new 會佔不同的mempry
		//this.start = function(){};
		//this.stop = function(){};
	}
	// add function by prototype
	// 每次 new 會佔相同的mempry
	// 但若為變數,設定個別值後就會佔不同的memory
	Car.prototype.start = function() {};
	Car.prototype.stop = function() {};
	// ----------------
	// callbacks function example
	function add(num1, num2) {
		var result;
		result = num1 + num2;
		return result;
	}
	function substract(num1, num2) {
		var result;
		result = num1 - num2;
		return result;
	}
	function multiply(num1, num2) {
		var result;
		result = num1 * num2;
		return result;
	}
	function calculate(num1, num2, operation) {
		var result;
		result = operation(num1,num2);
		return result;
	}
	// run 
	calculate(10, 20, add);
	calculate(10, 20, substract);
	calculate(10, 20, multiply);
	``` 

	* alert 
	```javascript
	alert("test in an external file");  
	```

	* prompt - 跳出輸入視窗(含標題)
	```javascript
	var p = prompt("How old are you?" ,"12 ?")
	if (p) {
		alert(p+ " is your age.")
	}
	else {
		alert("No input ant thing.")
	}
	```

	* setInterval
	```
	function time() {
		var d = new Date() ;
		document.write(d+"<br>");
	}
	var initiate = setInterval(function(){
		time();}, 1000);
			--> clear by clearInterval(initiate);
	```

	* setTimeour
	```
	var deleayAlert = setTimeout(function(){alert("Delayed")}, 3000);
	```

	* window.open

	```
	window.open("https://tw.yahoo.com/", "_blank", "height=200, width=200");
		target: _blank(另開視窗)..
	```

	*	consloe.log()
	```	
		console.log("let's go");
		console.log("%s has %d points", "Sam", 100);
		console.log("%cThis will be formatted with large, blue text", "color: blue; font-size: x-large");
	```

	*	requestAnimationFrame
	```javascript
	// 要求瀏覽器在刷新畫面前呼叫特定函數刷新動畫
	```
	*	setTimeout
	```
	setTimeout(function(){
			alart("hello")
		}, 3000);
	```

	* escape()/unescape()
	```
	對string編碼/解碼(非數字,字母編為16進制)
	"The escape test." --> The escape test.The%20escape%20test.

	在 JavaScript 1.5 及其後版本中，可以改用 encodeURI、decodeURI、
	encodeURIComponent、decodeURIComponent - 含功能性字元
	```

	* Date
	```
	Date.now() - from 1970 ms time
	// get
	var d = new Date();
	d.getDay() : 0~6, 0-sunday, 1-Monday 
	d.getDate() : 1~31
	d.getFullYear() : 1912
	d.getTimezoneOffset(): time offset from UTC minutes
	d.getTime() : time from 1910 to now(ms)
	d.getMonth(): 0~11
	d.getSeconds() : 0~59
	d.getMilliseconds(() : 0~999
	d.getMinutes() : 0~59
	d.gerHours() : 0~23
	// set
	var dt = new Date();
	dt.setFullYear(2008)
	dt.setMonth(5)
	dt.setDate(3)
	dt.setHours(10);
	dt.setMinutes(30);
	dt.setSeconds(12);
	setMilliseconds() 設置毫秒數 0~999

	// 日期中的日固定設為 0。例如 2014 的 2月份天數為。days 即是當月天數
	var days = new Date(2014,2,0).getDate();
	// 指定參數，日期時間字串則傳回參數的日期。
	document.write(new Date("2015/6/30 10:30:12"));
	```

	*	sizeof -"string"/"number"
	```javascript
	var age=30;
	sizeof age;
	```

	* get HTML5 中的 data-* attribute(\*字號的地方不能包含大寫字母)
	```javsscript
	// html
	<div id="slider" data-type="slideShow">
		<img class='photo' data-item="1" data-size="xs" src="http://fakeimg.pl/350x200/?text=Hello" />
		<img class='photo' data-item="2" data-size="lg" src="http://fakeimg.pl/550x200/?text=Welcome" />
	</div>
	// js
	let slider = document.getElementById('slider');
	console.log(slider.dataset.type);   //  "slideShow
	let photo = document.querySelectorAll('.photo');
	console.log(photo[0].dataset.item);   //  "1"
	console.log(photo[0].dataset.size);   //  "xs"
	```
	
* debug
	```
	try {
		// test code 
		//fun();
		var name = prompt("Your Name:");
		if (name.length > 5) {
			throw("long name..")
		}
	} catch(e) {
		// erroe event
		console.log(e);
		alert(e);
	} finally {
		// do correct and error
		console.log("debug end..");
	}
	```

* Regular Expressions(RegExp)
	* define
		```
		var MyRegExp = new RegExp(pattern, modifyers);
			or 
		var MyRegExp = /pattern/modifyers;

		// basic
		[adc]: a,b or c
		[^xyx]: not x,y or z
		[0-9]: 0~9
		[A-Z]: A~Z
		[a-z]: a~z
		(box|floor|bed|desk): box,floor,bed or desk
		yourWord: math YourWord
		// quantifier 數量
		g* : 0 to more "g"
		t? : 0 or 1 "t"
		z+ : 1 to more "z"
		a{X,}: a at least X
		a{X,Y}: a at least X to Y
		a{X}: match x number a
		^w: start wiyh "w"
		q$ : end with "q"
		// metacharacter 變化 - special character
		. : siggle character except for newlines
		\w: a word(leter)
		\W: not a word
		\d: a gigital
		\D: a non-digital character
		\s: a whitespace
		\S: a non-whitespace
		\b: begibning/end of a word
		\B: not begibning/end of a word
		\0: a nul
		\n: a new line LF:linux,CR+LF:window,CR:apple system
		\f: a line feed(換行)
		\r: a carriage return
		\t: a tab
		\v: a vertical tab (垂直定位)
		// modifyers
		i : case Insensitive or ignore-case
		g: global. It can found all match
		```

	* example
		```
		var myRegExp = /Kalob/g;
		var test = myRegExp.test("My name is Kalob");
			--> test is true
		var test = myRegExp.test("My name is Kallob");
			--> test is false	

		var myRegExp = /l{2}/g;
		var test = myRegExp.test("My name is Kallob");
			--> test is true
		var myRegExp = /kalob$}/g;
		var test = myRegExp.test("My name is Kalob");
			--> test is true

		var myRegExp = /kalob\n}/g;
		var test = myRegExp.test("My name is Kalob<br> test");
			--> test is false		
		var test = myRegExp.test("My name is Kalob\n test");
			--> test is true

		var myRegExp = /JS/gi;
		var test = myRegExp.test("This is a js class");
			--> test is true
		```
	
	*	Using
	```
	// test()
	var myRegExp = /Kalob/g;
	var test = myRegExp.test("My name is Kalob");

	// replace()
	var myRegExp = /sentence/gi;
	var str = "Change this sentence";
	dpcument.getElementById("demo6").innerHTML = str.replace(myRegExp, "string");
		--> "Change this string"

	// match()
	var myRegExp = /string/g;
	var str = "This is my test string string string".match(myRegExp);
	var matches = str.length;
		-->matches 3  (array 3 )
	var myRegExp = /string\s/g;
	var str = "This is my test string string string".match(myRegExp);
	var matches = str.length;
		-->matches 2
	```

* Navigator object for platform
	```
	platfrom: ie.Win32,..
	cookieEnabled: 
	onLine: it true 
	userAgent: 
	appName: browser name,ie.Netscape
	appVersion:browser ver
	appCodeName: name of you browser, ieMozilla

	// example 
	var navigationInfo = "platfrom: " + navigator.platfrom + "<br>";
	navigationInfo += "cookieEnabled: " + navigator.cookieEnabled + "<br>";
	navigationInfo += "onLine: " + navigator.onLine + "<br>";
	navigationInfo += "userAgent: " + navigator.userAgent + "<br>";
	navigationInfo += "appName: " + navigator.appName + "<br>";
	navigationInfo += "appVersion: " + navigator.appVersion + "<br>";
	navigationInfo += "appCodeName: " + navigator.appCodeName + "<br>";
	document.write(navigationInfo);

	// result - it is vary strange 
	platfrom: undefined
	cookieEnabled: true
	onLine: true
	userAgent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/71.0.3578.98 Safari/537.36
	appName: Netscape
	appVersion: 5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/71.0.3578.98 Safari/537.36
	appCodeName: Mozilla 
	```

* Ajax
	* some reference
	```
	// onreadystatechange : Defines a function to be called when the readyState property changes
	//readyState	Holds the status of the XMLHttpRequest. 
		0: request not initialized 
		1: server connection established
		2: request received 
		3: processing request 
		4: request finished and response is ready	
	// status
		200: "OK"
		403: "Forbidden"
		404: "Page not found"
		--------------------
		1xx: Information
		2xx: Successful
		3xx: Redirection
		4xx: Client Error
		5xx: Server Error
		[ref](https://www.w3schools.com/tags/ref_httpmessages.asp)
	// post Content-type
		application/x-www-form-urlencoded : 數據被編碼成以'&'分隔的鍵-值對,同時以'='分隔鍵和值.非字母或數字的字符會被 percent-encoding 
		application/json : json format
	```

	* example
	```
	// html
	<div id="getMe"></div>
	<div id="postMe"></div>
	// js
	function newAjax() {
		var ajax;
		if (window.XMLHttpRequest) {
			// this is for IE 7+, Chrome, Safri and fireFox
			ajax = new XMLHttpRequest();
		}
		else {
			// this is for IE6 and IE 5
			ajax = new ActiveXobjext("Microsoft.XMLHTTP")
		}
		return ajax;
	}

	function getMe() {
		var ajaxHandler = newAjax();
		ajaxHandler.onreadystatechange = function(){
			console.log("readyState=%d status=%d ", ajaxHandler.readyState, ajaxHandler.status);
			console.log(ajaxHandler);
			if (ajaxHandler.readyState==4 && ajaxHandler.status==200) {
				// json to object
				var respData = JSON.parse(ajaxHandler.responseText) ;
				console.log(ajaxHandler.responseText);
				console.log(respData);
				document.getElementById("getMe").innerHTML = ajaxHandler.responseText;
			}
		}
		ajaxHandler.open("get", "https://www.thef2e.com/api/signUpTotal", true);
		ajaxHandler.send();
	}
	getMe();

	function postMe() {
		var ajaxHandler = newAjax();
		var account = { email: "kyp001@yahoo.com.tw"};
		// object to JSON
		var data = JSON.stringify(account);
		console.log(account);
		console.log(data);

		ajaxHandler.onreadystatechange = function(){
			console.log("readyState=%d status=%d ", ajaxHandler.readyState, ajaxHandler.status);
			console.log(ajaxHandler);
			if (ajaxHandler.readyState==4 && ajaxHandler.status==200) {
				// json to object
				var respData = JSON.parse(ajaxHandler.responseText) ;
				console.log(ajaxHandler.responseText);
				console.log(respData);
				document.getElementById("postMe").innerHTML = ajaxHandler.responseText;
			}
		}
		ajaxHandler.open("post", "https://www.thef2e.com/api/isSignUp", true);
		ajaxHandler.setRequestHeader('Content-type', "application/json");
		ajaxHandler.send(data);
	}
	postMe();
	```

### DOM(Document Object Model - 文件物件模型
*	basic
	* querySector
	```javascript
	// method
		document.getElementById("")
	// action
		.onclick
	// property(屬性)
		.innertHTML
		.value (input type="text")
	// set css
		.style.display
	// set css varibale 
		// define
		:root {
			--circle-width: 100px;
		}	
		// use variable
		#circle	{
			width: var(--circle-width);
			height: var(--circle-width);
			border-radius: 50%;
			background-color: pink;
		}	
		// set css variable value
		var circleWidth = window.innerWidth/8 + "px" ;
		document.documentElement.style.setProperty("--circle-width", circleWidth);
		document.getElementById("circle").style.display = "block";
	// example
	//  innerHTML
		alert(document.getElementById("text").innerHTML);
		document.getElementById("text").innerHTML = "chane text";
	// onclick
		<button id="myButton">Press</button>
		document.getElementById("myButton").onclick = function(){
			alert("hello js");
	// set css
		document.getElementById("circle").onclick = function() {
			document.getElementById("circle").style.display = "none";
		}
	// get input type="text" value
		document.getElementById("text").innerHTML = document.getElementById("myInput").value;
	// -------------------------
	// > 下一層
	document.querySelector("div.img_box2 > img");
	var heroImage = document.querySelector("div.img_box2 > img");
	// get/set HTML attribute
	heroImage.getAttribute("src");
	heroImage.setAttribute("src", "https://images.pexels.com/photos/990826/pexels-photo-990826.jpeg?auto=compress&cs=tinysrgb&h=750&w=1260");
	```

	* some function
	```javascript
		document.write("<h1>Title</h1>");
	```

	* create Element
	```javascript
	var technologies = ["HTML", "CSS", "JS", "DOM"];
	function createMenu(items) {
	  var menu = document.createElement("ul");
	    items.forEach(function(element, index, array){
	    var item = document.createElement("li");
	    var textNode = document.createTextNode(element);
	    item.appendChild(textNode);
	    menu.appendChild(item);
	  });
	  document.body.appendChild(menu);
	}
	// run create menu
	createMenu(technologies);
	```

* event process
	*	event list

	```javascript
	document.addEventListener("mousemove", fun_name);
	```

	*	example 

	```javascript
	// HTML
	<body>
	  <ul class="menu">
	    <li class="menu-item">
	      <a href="#">Home</a>
	      <div class="menu-item-info">
	        This is the Home menu
	      </div>
	    </li>
	    <li class="menu-item">
	      <a href="#">About us</a>
	      <div class="menu-item-info">
	        This is the About us menu
	      </div>
	    </li>
	    <li class="menu-item">
	      <a href="#">Contract us</a>
	      <div class="menu-item-info">
	        This is the Contract us menu
	      </div>
	    </li>
	    <div class="clearfix"></div>
	  </ul>
	</body>
	// CSS
	body, * {
	  font-family: "Arial", sans-serif;
	  box-sizing: border-box;
	}
	.clearfix {
	  clear: both;
	}

	.menu {
	  background-color: #000;
	  list-style: none;
	  margin: 0;
	  position: relative
	}

	.menu-item {
	  float: left;
	}

	.menu-item a {
	  display: block;
	  color: white;
	  text-decoration: none;
	  padding: 1rem;
	}
	.menu-item a:hover {
	  color: #000;
	  background-color: #fff;
	}

	.menu-item-info {
	  display: none;
	  position: absolute;
	  left: 0;
	  width: 100%;
	  border: 1px solid #ddd;
	  border-top: none;
	  color: #333;
	  padding: 0.3rem;
	}

	.is-visible {
	  display: block
	}
	// JS
	var menuLinks = document.querySelectorAll(".menu-item > a");

	function displayInfoforMenu(event) {
	  var archor = event.target ;
	  var info = archor.parentNode.querySelector(".menu-item-info");
	  
	  info.classList.add("is-visible");
	}

	function hideInfoforMenu(event) {
	  var archor = event.target ;
	  var info = archor.parentNode.querySelector(".menu-item-info");
	  console.log(archor);
	  
	  info.classList.remove("is-visible");
	}

	for(var i=0 ; i<menuLinks.length ; i++) {
	  var archor = menuLinks[i];
	  archor.addEventListener("mouseover", displayInfoforMenu);
	  archor.addEventListener("mouseout", hideInfoforMenu);
	}
	```

* flow
	* for in array
	```javascript
		var myArray = ["Bill", "David", "Mary"];
		for (var n in myArray) {
			document.write(n+"<br/>");	//0,1,..
			document.write(myArray[n]+"<br/>");	// Bill..
	```

* example 
	*	mouse 追蹤滑鼠軌跡  
	simple 
	```css
		// htlm
		<div id="ball">
			<div class="halo"></div>
			<div class="halo"></div>
			<div class="halo"></div>
		</div>		
		// css
		* {
			margin: 0;
		}
		:root {
			--mouse-x;
			--mouse-y;
			--radius: 40px;
		}
		#ball {
			width: var(--radius);
			height: var(--radius);
			background-color: #ffe13d;
			border-radius: 50%;
			position: absolute;
			transform: translate(calc(var(--mouse-x)*1px - var(--radius)/2 ), calc(var(--mouse-y)*1px - var(--radius)/2));
		}
		// js
		var mouse_x=0, mouse_y=0;
		document.addEventListener("mousemove", (event) => {
			mouse_x = event.clientX;
			mouse_y = event.clientY;
		});
		function delayMotion() {
			document.documentElement.style.setProperty("--mouse-x", mouse_x);
			document.documentElement.style.setProperty("--mouse-y", mouse_y);
			requestAnimationFrame(delayMotion);
		}
		delayMotion();
	```

	add delay 
	```css
		// js
		var mouse_x=0, mouse_y=0;
		var ball_x=0, ball_y=0;
		var distent_x=0, distent_y = 0; 
		const strength = 0.3;
		document.addEventListener("mousemove", (event) => {
			mouse_x = event.clientX;
			mouse_y = event.clientY;
		});

		function delayMotion() {
			distent_x = mouse_x - ball_x;
			distent_y = mouse_y - ball_y;

			ball_x += distent_x*strength;
			ball_y += distent_y*strength;
			document.documentElement.style.setProperty("--mouse-x", ball_x);
			document.documentElement.style.setProperty("--mouse-y", ball_y);
			requestAnimationFrame(delayMotion);
		}

		delayMotion();
	```

	add 光環
	```css
		// css
		* {
			margin: 0;
		}

		:root {
			--mouse-x;
			--mouse-y;
			--radius: 40px;
			--factor: 1;
			--scare;
		}
		#ball {
			width: var(--radius);
			height: var(--radius);
			background-color: #ffe13d;
			border-radius: 50%;
			position: absolute;
			transform: translate(calc(var(--mouse-x)*1px - var(--radius)/2 ), calc(var(--mouse-y)*1px - var(--radius)/2));
		}

		.halo {
			width: var(--radius);
			height: var(--radius);
			background-color: #ffe13d;
			border-radius: 50%;
			opacity: 0.15;
			position: absolute;
			transform: scale(calc(var(--factor)*var(--scare)));
		}
		.halo:nth-child(1) {
			--factor: 0.3;
		}
		.halo:nth-child(2) {
			--factor: 0.5;
		}
		.halo:nth-child(3) {
			--factor: 0.9;
		}
		// js
		var mouse_x=0, mouse_y=0;
		var ball_x=0, ball_y=0;
		var distent_x=0, distent_y = 0; 
		const strength = 0.3;
		var vel_x=0, vel_y=0;
		const drop=0.15;

		document.addEventListener("mousemove", (event) => {
			mouse_x = event.clientX;
			mouse_y = event.clientY;
		});

		function delayMotion() {
			distent_x = mouse_x - ball_x;
			distent_y = mouse_y - ball_y;

			ball_x += distent_x*strength;
			ball_y += distent_y*strength;

			document.documentElement.style.setProperty("--scare", (distent_x+distent_y)*drop);
			document.documentElement.style.setProperty("--mouse-x", ball_x);
			document.documentElement.style.setProperty("--mouse-y", ball_y);
			requestAnimationFrame(delayMotion);
		}

		delayMotion();
	```