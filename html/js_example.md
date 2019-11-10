## [HTML Guide](./html_guide.md)

## Javascript example

* onclick call js functoion  

```html
<p id="demo" onclick="myFunction()">Click me to change my text color.</p>
<button class="btn" onclick='myFunction2()'><i class="fa fa-trash" aria-hidden="true"></i></button>
<button type="button" class="btn" onclick='myFunction2()'><i class="fa fa-trash" aria-hidden="true"></i></button>
<button onclick="myFunction2()">Click me</button>
<p id="demo2"></p>

<script>
function myFunction() {
  document.getElementById("demo").style.color = "red";
	console.log("myFunction")
}
function myFunction2() {
  document.getElementById("demo2").innerHTML = "Hello World";
}
</script>
```