# Css issue

*   [Root](../README.md)
*   [1. inline-block 不接受 margin-left/margin-right](#a1)
*   [2. img 放於 div 內都會在底部保留一些間隔](#a2)
*   [3. CSS inline-block 間空白移除](#a3)
*   [4. button shows blue outline when clicked](#a4)
*   [5. ???? 有些地方 clear:both not working ????](#a5)

<h2 id="a1">1. inline-block 不接受 margin-left/margin-right</h2>

```
因 inline-block 為行內元素故不接受
```


<h2 id="a2">2. img 放於 div 內都會在底部保留一些間隔</h2>

```
1. img 設定 display: block or vertical-align: middle 即可去除

div 
	img 
		display: block

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