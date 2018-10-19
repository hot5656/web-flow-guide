# HTML record

*   [Root](../README.md)
*   [1. emmet](#a1)
*   [2. lorem 假字](#a2)
*   [3. 版型思考](#a3)
*   [4. variable](#a4)
*   [5. basic struct](#a5)
*   [6. tag](#a6)


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
meta:vp :　<meta name="viewport" content="width=device-width, initial-scale=1.0">
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

<h2 id="a4">[4. variable</h2>

```
$width: 940px
$body-bg: 
$text-color:pink→預設文字顏色
$font-color:    →強調文字顏色
$link-color:#000→文字連結樣式，多則就再加紹數字
$link-color-hover:#fff→滑鼠拖曳過後的樣式顏色
$font-size:13px→全域字型大小，如一網站有多種就下多種字型
$line-height:1.8→全域行距
$container-width:960px→ 網站整體寬度
$font-style："Helvetica Nueue", Arial, Sans Serif; →全域字型
$line-height: 1.6
```


<h2 id="a5">5. basic struct</h2>

```html
	<div class="wrap">
		<header></header>
		<div class="content"></div>
		<footer></footer>
	</div>
```

<h2 id="a6">6. tag</h2>

```html
<header>：網頁的標頭，通常放置網站標題。
<nav>：網頁的選單、導覽。
<main>：網頁的主要內容。
<aside>：網頁的側欄、附加內容。
<article>：一篇文章內容。
<section>：自訂的區塊，例如數篇摘要組成的空間。
<footer>：網頁的頁尾，通常放置聯絡方式、著作權宣告等等。
<mark>：強調一小塊內容。
<time>：顯示日期時間。

<em>
```
