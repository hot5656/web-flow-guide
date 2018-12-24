# HTML List

*   [Root](../README.md)

### table
```html
<table class="style1">
  <tr>
    <th>標題</th>
    <th>標題</th>
  </tr>
  <tr>
    <td>內容</td>
    <td>內容</td>
  </tr>
</table>

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
*	name (可重複)
	```
	1. 作為可與伺服器交互資料的HTML元素的伺服器端的標示，比如input、select、textarea、和button等。我們可以在伺服器端根據其Name通過Request.Params取得元素送出的值。
	2. HTML元素Input type='radio'分組，我們知道radio button控件在同一個分組類，check操作是mutex的，同一時間只能選中一個radio，這個分組就是根據相同的Name屬性來實現的。
	3. 建立頁面中的錨點，我們知道<a href="URL">link</a>是獲得一個頁面超級連結，如果不用href屬性，而改用Name，如：<a name="PageBottom"></a>，我們就獲得了一個頁面錨點。
	4. ?? 作為對象的Identity，如Applet、Object、Embed等元素。比如在Applet對像實例中，我們將使用其Name來引用該對象
	5. ??  在IMG元素和MAP元素之間關聯的時候，如果要定義IMG的熱點區域，需要使用其屬性usemap，使usemap="#name"(被關聯的MAP元素的Name)。
	6. ?? 某些特定元素的屬性，如attribute，和param。例如為Object定義參數<PARAM NAME = "appletParameter" VALUE = "value">。
	```

* element 
	```html
	// button
		<button type="button">我是按鈕</button>
	// tag a
		<a href="index.html" class="next">繼續逛逛</a>
		<a class="pay" href="checkout_profile.html">結帳</a>
	// icon 語法
		.ico語法1：
		<link rel="shortcut icon" href="圖示網址/favicon.ico" />
		.ico語法2：
		<link rel="icon" href="圖示網址/favicon.ico" type="image/ico" />
	// hr - 分隔線
		<hr>
	// a link but no do anything
		<a href="javascript: void(0)">Link</a>
	// <b>: bold
		<b></b>
	```