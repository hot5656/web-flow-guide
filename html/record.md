# HTML record

*   [Root](../README.md)
*   [1. emmet](#a1)
*   [2. lorem 假字](#a2)
*   [3. 版型思考](#a3)

<h2 id="a1">1. emmet</h2>

```
// 多層 {}:內容
.warp>.menu>ul>li*6>a{hello}

// $=index number
.style${hello}*3

// + 產生同一層
.box+p+h3

// ^ 跳回上一層
div>h3+p^div

// () 可分開
(nav>ul>li*4)+(article>h3>p)

// .:class #:id
.wrap>#header>p.a1.a2

// [] 加入 attribute
img[src="test.jpg" alt="test"]

// {} 內容
P{This is a key}

//@ 起始值
ul>li.item$@5*4

// css 縮寫
m10 : margin: 10px
p10p20p : padding: 10% 20%
fl : float: left
fz16 : font-size: 16px
bd3-s#3  : border: 3s #333333

// html 縮寫
! : HTML5 structure
meat:vp :　<meta name="viewport" content="width=device-width, initial-scale=1.0">
					　<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no"

```

<h2 id="a2">2. lorem 假字</h2>

```
lorem10 : 10字
```


<h2 id="a3">3. 版型思考</h2>

```
(1)背景沒考慮銀幕解析度來去做延伸
(2)元素內的文字沒考慮如果呈現多行時，設計也必須延伸
(3)網頁字型沒考慮到網頁預設字型
(4)hover過後的按鈕樣式並未提供
(5)沒有grid的觀念，每個頁面元素寬度不一
(6)設計的頁面沒辦法程式化
(7)動畫效果過於複雜，無法於時程內完工
- 是否缺功能圖:下拉是選單,功能圖
- 有些圖切透明
- 字型確認
- layout class/structure design
- png copy to one file
```




