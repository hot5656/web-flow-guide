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