# Javascript List

*   [Root](../README.md)
*   [JavaScript 基礎](https://developer.mozilla.org/zh-TW/docs/Learn/Getting_started_with_the_web/JavaScript_basics)
*   [w3schools JavaScript](https://www.w3schools.com/js/default.asp)




### basic
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
	--------------------
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
	```
* object
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
	-----------
	var usetr;
	user = {	
		login: "",
		password: "",
		firstName: "",
		lastName: "",
		"full name": ""
	};
	user["login"]
	user["full name"]
	--> var propertyToAccess = "firstName";
	    user.propertyToAccess
	    user[propertyToAccess]
	```


* function
	* define
	```javascript
	function fun_name(para1, para2) {
		....
		return;
	}
	``` 
	* alert 
	```javascript
	alert("test in an external file");  
	```
	*	sizeof -"string"/"number"
	```javascript
	var age=30;
	sizeof age;
	```
