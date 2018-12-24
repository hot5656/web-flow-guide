# jQuery List

*   [Root](../README.md)

### basic
*	check jQuery load success
	```javascript
	<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
	// ----------------
	<script>
		$(window).ready(function(){
			alert("loaded");
		});
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
	$(window).ready(function(){
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

* function
	```
	$("textarea").css("display", "none");
	$(this).blur();
	$(this).css("border", 0);
	$(this).next().toggle();
	$(this).append("Mouse Down. ");
	$(this).innerHTML = "test...);
	$("#input").focus();
	```