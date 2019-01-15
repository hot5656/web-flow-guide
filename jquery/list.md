# jQuery List

*   [Root](../README.md)

### basic
*	window/document and ready/onload
	```
	window/document: 
		1. window代表的是瀏覽器視窗
		2. document代表的是瀏覽器視窗中載入的dom元素
			資料多 document > window
	ready/onload
		1. load事件主要就是用來代替原生的window.onload
		2. load事件需要頁面完全載入完成才可以觸發: 所謂的完全載入完，不僅僅是dom結構載入完，還需要所有的連結引用都載入完才可以。比如頁面中有大量圖片，必須等每一個圖片都載入完成，才叫完全載入完
		3. $(document).load(fn);這是錯誤的寫法，根本不會執行
		4. ready事件可以加在任意元素上,ready事件不要求頁面完全載入完，只需要載入完dom結構即可觸發。
		5. $(document).ready(fn);相容性、安全性是最好的，如果有此類需求，儘量採用這種方式。
	js : 使用 window.onload()
	jQuery : 使用 $(document).ready()
	```

*	check jQuery load success
	```javascript
	<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
	// ----------------
	<script>
		$(document).ready(function(){
			alert("loaded");
		});
		/*
		or 
		$(function(){
			....code
		});
		*/
	</script>
	```

*	$('..') : sector
	```
	var MyId = $('#elementId');
	var allBolds = $('.bold');
	var theBody = $('body');
	var allName = $('[name="testName"]');
	var divName = $('div[name="testName"]');
		<div name="testName">Div 1</div>
		<span name="testName">Span 1</span>
	```

* event
	```javascript
	// blur: unfocus
	// html
	<textarea id="demoTextarea" placeholder="click in me"></textarea>
	// --------
	<input type="text" placeholder="click in me">
	// --------
	<button id="focus">Button</button>
	<input id="input" type="text">
	// --------
	<input id="inputThenBlur" type="text">
	// --------
	<div class="demo1">Hover the mouse over me!</div>
	// --------
	<div id="mouseEvent">MouseDown in here </div>
	// --------
	<button type="button" id="buttonToggle">Click me</button>
	<span>I will be toggle!</span>	
	// js
	$(document).ready(function(){
		$("textarea").focus(function(){
			$("textarea").css("display", "none");
		});
		// --------
		$("#focus").click(function(){
			$("#input").focus();
		});
		// --------
		$("#inputThenBlur").focus(function(){
			$(this).blur();
		});
		// --------
		$("div.demo1").hover(
			function(){
				// mouse over the element
				$(this).css("border", "1px solid red");
			},
			function(){
				// mouse not over the element
				$(this).css("border", 0);
			}
		);
		// --------
		// keypress(),keydown(),keyup()
		$("#demoTextarea").keypress(function(){
			alert("Key was presses!")
		});
		// --------
		//mousedown()/mouseup()
		//mouseover()/mouseout()
		//mouseenter()/mouseleave()
		//mousemove()
		$("#mouseEvent").mousedown(function(){
			$(this).append("Mouse Down. ");
		});
		$("#mouseEvent").mouseup(function(){
			$(this).append("<b>Mouse up.</b> ")
		});
		// --------
		//click()/dblclick()
		//focusin()/focusout()
		//hover()
		//toggle(): switch between hide and show
		$("#buttonToggle").click(function(){
			$(this).next().toggle();
		});
		// dblclick()
		$("#buttonToggle").dblclick(function(){
			alert("Double clicked!");
		});		
	});
	// -------------
	<!-- normal submit get page -->
	<form action="index.html" id="form2">
		<input type="text" id="name2">
		<input type="submit" value="submit">
	</form>
	// js - if want to check condition
	$("#form2").submit(function() {
		if ($("#name2").val() === "") {
			return false;
		}
	});	
	<!-- jQuery do submit -->
	<form action="index.html" id="form1">
		<input type="text" id="name">
		<input type="button" value="submit" id="validate">
	</form>
	// js
	$("#validate").click(function() {
		// if set value : $(this).val("click");
		// get value function
		if ($("#name").val() != "") {
			// need form id
	  	$("#form1").submit();
	  }
	});			
	```

* key press
	```javascript
	// html
	<textarea placeholder="click in me"></textarea>
	// js
	$("textarea").keypress(function(event){
		var keyCode = (event.keyCode ? event.keyCode : event.which) ;
		console.log("keypress : " + keyCode);
	});
	$("textarea").keydown(function(event){
		var keyCode = (event.keyCode ? event.keyCode : event.which) ;
		console.log("keydown : " + keyCode);
	});
	$("textarea").keyup(function(event){
		var keyCode = (event.keyCode ? event.keyCode : event.which) ;
		console.log("keyup : " + keyCode);
	});
	```

* function
	* effect 效果
	```javascript
	// function
	.hide(speed)/.show(speed)/.toggle(speed) : toggle hide/show (往左消失)
	.fadeOut()/.fadeOut()/.fadeToggle() : 退色
	.slideUp()/.slideDown()/.slideToggle() : 往下滑出
	speed: 
		space - instantly
		"fast" - 200ms
		"slow" - 600ms
		number - ms
	// example
	// html
	<button id="demo" type="button">Toggle text!</button>
	<span id="toggleMe1">Toggle me!</span>
	<span id="toggleMe2">Toggle2 me!</span>
	<span id="toggleMe3">Toggle3 me!</span>
	// js
	$("button#demo").click(function(){
		$("#toggleMe1").toggle("slow");
		$("#toggleMe2").fadeToggle("slow");
		$("#toggleMe3").slideToggle("slow");
	});
	// call back 
	$("#toggleMe3").slideToggle("slow", function(){
		alert("slide complete.");
	});	
	// slide up trige slide down
	// html
	<button id="selectElement" type="button" style="display: block">Slide</button>
	<textarea id="slideElement" name="" id="" cols="30" rows="10" style="border: 1px solid red"></textarea>
	// js
	$("#selectElement").click(function(){
		$("#slideElement").slideUp(function(){
			$(this).slideDown(3000);
		});
	});
	```

	* html()
	```javascript
	// html 
	<button>Change HTML</button>
	<div id="myDiv">Old text</div>
	// js
	$("button").click(function(){
		$("#myDiv").html("Chenge text.");
		alert($("#myDiv").html());
	});
	```

	* change css
	```
	// html
	<button id="demo">Change CSS</button>
	// js
	$("button#demo").click(function(){
		$(this).css("background-css", "black");
		$(this).css("color", "white");
		$(this).css("border", 0);
	});
	$("button#demo").focus(function(){
		$(this).css("outline", 0);
	});
	```

	* set/get HTML attribute
	```javascript
	// html
	<div id="demoDiv" title="test title">demo dev</div>	
	// js
	$(document).ready(function(){
		var divDemo = $("#demoDiv")
		divDemo.click(function(){
			alert(divDemo.attr("title"));
			divDemo.attr("title","change title");
			alert(divDemo.attr("title"));
		});
	```

	*	set/get HTML5 中的 data-* attribute(\*字號的地方不能包含大寫字母)
	```javascript
	// html
	<div id="demoDiv" data-number="23">demo dev</div>	
	// js
	$(document).ready(function(){
		var divDemo = $("#demoDiv");
		divDemo.click(function(){
			alert(divDemo.data("number"));
		});
	});
	```

	*	ajax
	```javascript
	// simple load file -----------
	// html
	<div id="ajaxMe">Static text</div>
	// js
	$("#ajaxMe").click(function(){
		$(this).load("https://www.thef2e.com/api/signUpTotal");
	});
	// get ------------
	// html
	<button>Click me</button>
	<div id="ajaxDiv">&nbsp;</div>
	// js
	// get 
	$("button").click(function(){
		$.ajax({
			dataType: "json",
			url: "https://www.thef2e.com/api/signUpTotal",
			success: function(data){
				console.log(data);
				console.log(JSON.stringify(data));
				// JSON.stringify(data) : object to string(mean JSON)
				$("#ajaxDiv").html("respData:"+JSON.stringify(data));
			},
			error: function(err) {
				console.log(err);
			}
		});
	});	
	// post ----------
	var account = { email: "kyp001@yahoo.com.tw"};
	$("button").click(function(){
		$.ajax({
			// set post
			type: "post",
			// set post data, JSON.stringify(data) : object to string(mean JSON)
			data: JSON.stringify(account),
			// set data type
			contentType: "application/json",
			dataType: "json",
			url: "https://www.thef2e.com/api/isSignUp",
			success: function(data){
				console.log(data);
				console.log(JSON.stringify(data));
				// JSON.stringify(data) : object to string(mean JSON)
				$("#ajaxDiv").html("respData:"+JSON.stringify(data));
			}
		});
	});
	```

	* animaion(動畫)
	```
	// html
	<div id="box1" style="height: 100px; width: 100px; border: 1px solid red"></div>
	<div id="box2" style="height: 100px; width: 100px; border: 1px solid red"></div>
	// css
	$("#box1").hover(
		function(){
			$(this).animate({width: "+=100"});
		},
		function(){
			$(this).animate({width: "-=100"});
		}
	);

	$("#box2").hover(
		function(){
			$(this).animate(
				{
					width: 200,
					height: 200,
					borderWidth: "10px"
				},
				2500,
				function(){
					alert("Finished animated-callback")
				}
			);
		},
		function(){
			$(this).animate(
				{
					width: 100,
					height: 100,
					borderWidth: "1px"
				},
				2500,
				function(){
					alert("Return animated-callback")
				}
			);
		}
	);
	```

	*	other
	```
	$("textarea").css("display", "none");
	$(this).blur();
	$(this).css("border", 0);
	$(this).next().toggle();
	$(this).append("Mouse Down. ");
	$(this).innerHTML = "test...);
	$("#input").focus();
	```