# Css issue

*   [Root](../README.md)
*   [1. inline-block 不接受 margin-left/margin-right](#a1)
*   [2. img 放於 div 內都會在底部保留一些間隔](#a2)
*   [3. CSS inline-block 間空白移除](#a3)
*   [4. button shows blue outline when clicked](#a4)
*   [5. ???? 有些地方 clear:both not working ????](#a5)
*   [6. 去除邊框](#a6)
*   [7. ul li 水平排列中間會有空格](#a7)
*   [8. material.io icon 置中](#a8)
*   [9. checkbox 與文字對齊下標](#a9)
*   [10. select set margin-left 誤差 4px 調整](#a10)
*   [11. flex justify-content 多行 間隔 issue](#a11)


<h2 id="a1">1. inline-block 不接受 margin-left/margin-right</h2>

```
因 inline-block 為行內元素故不接受
```


<h2 id="a2">2. img 放於 div 內都會在底部保留一些間隔</h2>
原因 : image vertical-align: baseline;  

```css
1. img 設定 display: block

div 
	img 
		display: block

2. img 設定 vertical-align: middle
div 
	img 
		vertical-align: middle
```

<h2 id="a3">3. CSS inline-block 間空白移除</h2>

```
// 使用 inline-block 會有隱藏空白的問題，造成寬度計算錯誤
實際測試 Browser 對 inline-block 的實作，結果如下圖，兩個 inline-block 中間會有 4px 的空白
設定 margin 為負值，硬是將兩個 Element 拉近即可
.inline-block {
    margin-right: -4px;
}
```

<h2 id="a4">4. button shows blue outline when clicked</h2>

```
.btn:focus {
  outline: none;
}

```


<h2 id="a5">5. ???? 有些地方 clear:both not working ????</h2>

<h2 id="a6">6. 去除邊框</h2>

```
border-width: 0
```


<h2 id="a7">7. ul li 水平排列中間會有空格</h2>

```
在 <ul> 上縮小字體大小到 0並在 <li> 上恢復大小
```

<h2 id="a8">8. material.io icon 置中</h2>

```css
    i 
      vertical-align: middle
```

*   [9. checkbox 與文字對齊下標](#a9)


<h2 id="a9">9. checkbox 與文字對齊下標</h2>

```css
  [type="checkbox"]
    margin-left: 9%
    margin-bottom: 22px
    vertical-align: sub

<input type="checkbox" id="check">
<label for="check">記住我</label>
```


<h2 id="a10">10. select set margin-left 誤差 4px 調整</h2>

```css
.item-2
  width: 48.5%
.item-2-2nd
  margin-left: 3%
  width: 48.5%
.item-2-2nd-s
  margin-left: calc(3% - 4px)

<select name="city" class="item-2">
　<option value="Taipei">台北</option>
　<option value="Taoyuan">桃園</option>
　<option value="Hsinchu">新竹</option>
　<option value="Miaoli">苗栗</option>
</select>
<select name="area" class="item-2-2nd-s">
　<option value="Taipei">三民區</option>
　<option value="Taoyuan">苓雅區</option>
　<option value="Hsinchu">前鎮區</option>
　<option value="Miaoli">新興區</option>
</select>
```

<h2 id="a11">11. flex justify-content 多行 間隔 issue</h2>

```
--> clearfix 造成影響

.row
	margin: 0 auto
	padding-top: 30px
	width: 1000px
	// +clearfix()
	display: flex
	flex-wrap: wrap
	// align-items: flex-start
	// align-content: flex-start
	// justify-content: space-around 
	justify-content: space-between
```