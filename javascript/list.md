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
	sentence.charAt(0)
	sentence.charAt(3)
	sentence.charAt(sentence.length-1)
	// -- add str and number
	"abc " + number + " end"
	```
* Math 
	Math.pow(x, y) - x y 次方
	Math.random() - random 0 to 1 (not include 1)
	Math.floor(x) - 轉成整數,無條件捨去
	Math.round(x) - 轉成整數,無條件進入
* color 
	rgba(a,b,c,d) : d - 透明度 1:不透明
* arrays and implicit iteration
	```javascript
	// define
	var myArray = [];
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
	// normal use
	window.innerWidth: 視窗寬度 
	window.innerHeight: 視窗高度
			or 
	// document.documentElement - root element of the document
	document.documentElement.clientWidth: 視窗寬度(can use not include padding,margin,scoll...)
	document.documentElement.clientHeight:  視窗高度

* function
	* define
	```javascript
	function fun_name(para1, para2) {
		....
		return;
	}
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

	*	consloe.log()
	```	
		console.log("let's go");
	```

	*	setTimeout
	```
	setTimeout(function(){
			alart("hello")
		}, 3000);
	```

	* Date
	```
	Date.now() - from 1970 ms time
	```

	*	sizeof -"string"/"number"
	```javascript
	var age=30;
	sizeof age;
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
	heroImage.getAttribute("src");
	heroImage.setAttribute("src", "https://images.pexels.com/photos/990826/pexels-photo-990826.jpeg?auto=compress&cs=tinysrgb&h=750&w=1260");
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
	
