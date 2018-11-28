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
