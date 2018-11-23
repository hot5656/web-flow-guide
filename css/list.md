# Css List

*   [Root](../README.md)

*	block
	* border  
	border: 5px solid red  
  border: none  
  *	clear 清除float效果
	left：消除左邊的浮動  
	right：消除右邊的浮動  
	both：消除左右兩邊的浮動  
	none：預設值，不消除任何一邊的浮動  
	inherit：繼承浮動，IE未支持此屬性值  
	*	box-sizing - box size 不受 padding and border 影響  
  box-sizing: border-box;  
  * parent number  
	&:first-child  由 parent 眼光看(first-child)
	&:nth-child(3n) 3的倍數
	* z-index: 10; 數字大的在上層,應該最大值30足夠
	*	color: inherit; 繼承
*	< ul >
  *	no icon  
  list-style-type: none;  
  *	水平  
  display:inline;   
  *	list-style-type  
    none (沒有)  
    disc (全黑圓圈)  
    circle (空心圓圈)  
    square (正方形)  
    upper-latin (大寫拉丁文)  
    lower-latin (小寫拉丁文)  
    upper-roman (大寫羅馬文)  
    lower-roman (小寫羅馬文)  
    upper-alpha (大寫希臘文 )  
    lower-alpha (小寫希臘文 )  
  list-style-position :  inside/outside(default)  
  list-style-image : url("circle.gif")  
  list-style : list-style: url("circle.gif") none inside; 
*	< a >
  *	無底線 text-decoration: none;  
  *	&:hover
*	< img > 
  *	垂直置中 : vertical-align:middle;  
  * 水平置中 :  
  	display: block
  	margin: auto
  *	clip-path: inset(10% 0 10% 0);  
  *	need set inline-block ,width and height  
  *	background-size: cover;  
		auto	預設值，維持背景圖片原本的大小。  
		length	自訂背景圖片的大小，可以用兩個數字表示，先是設定寬度，再來是設定高度，不可為負數，如果只寫一個數字，第二個數字則會自動設為 auto 的效果，背景圖片自動縮放。  
		percentage	自訂背景圖片的大小，用兩個數字百分比表示，第一個數字百分比是設定寬度，第二個數字百分比是設定高度，如果只寫一個，則第二個將自動設為 auto 的效果，背景圖片自動縮放。  
		cover	使用於背景圖片小於容器時，將背景圖片的大小放大至容器的大小並填滿，缺點是如果容器的長寬比例與背景圖片的長寬比例不吻合，會出現背景圖片失真的情況。  
		contain	使用於背景圖片大於容器時，將背景圖片縮小至可以在容器內呈現。  
  *	background-position: center center;  
  *	background-image: url("../../img/photo-1473256599800-b48c7c88cd7e.jpg");  
		```css
		background-repeat: 
			no-repeat 背景圖案不重複
			repeat-x 背景圖案在 x-方向重複
			repeat-y 背景圖案在 y-方向重複
			repeat  背景圖案在 x- 及 y-方向重複
		background-attachment: 
			fixed 背景圖案永遠是停留
			scroll 背景圖案將與捲動的動作一起移動
		background-position: [top,center,bottom,%,x position]  [left,center,right,%,y position] 
		background-size：bg-size , bg-size
			auto(預設值)	即背景圖片原始長寬
			length 				指定圖片具體大小的數值，不允許負值(當只設定一個數值，另一個數值預設值為auto)
			percentage		以背景圖所在元素的百分比指定背景圖大小，不允許負值(
			cover					主要用於背景圖小於所在的內容，此時就可以採用cover的方式，使背景圖放大至內容的大小，但此方法容易使背景圖因放大而失真
			contain				主要用於背景圖大於所在內容，但卻需要將背景圖完整呈現，此時就可採用contain的方式，使背景圖縮小至內容的大小。
		```


  *	white-space: 空白的處理方法  
    normal(default)   連續的空白字都縮減為一個空白，長行遇到右邊界會跳行分為兩行 
    nowrap 連續的空白字會縮減為一個空白，不跳行  
  *	text-indent 首行  
     text-indent : 36px 首行縮排  
     text-indent : -36px 首行凸出來  
*	text
  *	水平置中 text-align:center;(display: block;)  
  *	垂直置中 line-height as parents height  
  *	height: 50px  
  *	line-height: 50px  
  *	text-align: center  
  *	letter-spacing: 1px; 字間隔
  *	text-decoration 
  none        : 預設值，不顯示任何文字特效  
  overline    : 替文字增加上線  
  underline   : 替文字增加底線  
  line-through: 替文字增加刪除線  
  blink       : 替文字增加閃爍效果，已取消  
  inherit     : 繼承自父層的文字效果  
	*	font-weight  
	normal - 這是預設值，可以不用設定。  
	bold - 粗體字。  
	bolder - 更粗的字型，不過用起來跟 bold 似乎沒什麼差異。  
	lighter - 細體，不過與 normal 沒什麼差異。  
	數字 - 可以設定的有 100、200、300、400、500、600、700、800、900。  
* 字型
  * serif - 襯線體，是一種字體的裝飾。這類字體的每一個字母都會有一些小小的突起，筆畫的粗細也不相同。一般常見的字型有：Caslon、Courier、Garamond、Lucida、Sabon、Times New Roman…等等 對應到中文有點像是黑體字
  * Sans-serif - 無襯線體，這類字體有點像麥克筆寫的，沒有多餘的裝飾，有一說是從襯線體的一類演變出來的。通常這類字體看起來會比較現代，因為襯線體是從羅馬時代就有的字體型態，歷史悠久，當然自然就有一種古典的感覺。常見的字型有：Avenir、DIN、Frankin Gothic、Frutiger、Futura、Helvetica、Univers…等等
  * font-family : 字體的類別 verdana,arial,impact
  * font-size : 字體的大小  
    9px, 150%, 0.8cm, 1.2em, 1.2rem,small,large
  * font-weight : 字體的厚度  
    100~900, bold(厚體)
  * font-style 屬性是用來設定字體是否為斜體字 (italic 或 oblique)
  * font-variant 屬性是用來設定文字是不是要以小型大寫 (small caps) 字體顯現。在小型大寫字體中，所有的字母都是大寫，可是字體是比一般大寫來得小。可能的值為 "small-caps" 和 "normal"。
*	CSS3 動畫
	*	transition -hover, focus(如果不透過 JavaScript 事件處理)  
	transition: property duration timing-function delay;  
	ransition-property 用來定義可以產生 transition 屬性效果的屬性名稱，例如寬度、背景顏色 ...。  
	transition-duration 用來定義 transition 屬性發生的時間，單位為秒。  
	transition-timing-function 用來定義 transition 效果的發生速度，可說是設定轉場時所依據的貝茲曲線。  
	transition-delay 用來定義多久之後開始發生 transition 效果。  
	```
	.box  
		height: 50px 
		width: 50px 
		transition: all 1s 
		&:hover 
			width: 300px
	```
	*	只對單一屬性加入 transition  
	```
	.box:hover {
	  width: 200px;
	  height: 200px;
	  transition: height 1s;		
	}  
	```
	*	對不同屬性同時做 transition
	transition: 1s height, 2s width;
	*	先變換一個屬性，再變換另一個屬性
	transition: height 1s, width 1s 1s;
	*	雙向的 transition  
	```
	.box
		height: 50px
		width: 50px
		transition: all 1s
		&:hover
			height: 300px
			width: 300px
			transition-timing-function: ease
			transition: height 1s	  
	```
	*	transition-timing-function  
	// transition-timing-function: ease-in  
	// transition: height 3s ease-in  
	// transition: all 1s cubic-bezier(0.250, 0.250, 0.750, 0.750)　　//平均速度  
	linear: 匀速  
	ease: 急加速後減速 (預設值)  
	ease-in: 加速  
	ease-out: 减速  
	ease-in-out: 較平緩的 ease  
	cubic-bezier: 自定義速度模式  
	*	無法使用 transition  
	height: auto (不確定的值) 至 height: 100px (具體數值)  
	display: none 至 display: block  
	background: url(foo.jpg) 至 background: url(bar.jpg)  
* transform: transform-function;
	* rotate(θ)
	指定元素以參考點為中心軸 2D 旋轉 θ 度。
	* skewX(θ)
	指定元素以參考點為中心軸沿著橫向傾斜 θ 度。
	* skewY(θ)
	指定元素以參考點為中心軸沿著縱向傾斜 θ 度。
	* skew(θx,θy)
	指定元素以參考點為中心軸沿著橫向傾斜 θx 度、 縱向傾斜 θy 度。參數如果只指定 1 個，省略的第 2 個參數，會視為 0 ，也就是只有沿橫向傾斜。September, 2012 W3C 草書又復原此項
	* scaleX(m)
	指定元素由參考點橫向縮放 m 倍。
	* scaleY(m)
	指定元素由參考點縱向縮放 m 倍。
	* scale(mx,my)
	指定元素由參考點 2D 橫向縮放 mx 倍、縱向縮放 my 倍，等於是結合 scaleX(mx), scaleY(my) 。參數如果只指定 1 個，省略的第 2 個參數，會等於第 1 個，也就是橫向、縱向以相同比例縮放。
	* translateX(o)
	指定元素由參考點橫向移動 o 距離。
	* translateY(o)
	指定元素由參考點縱向移動 o 距離。
	* translate(ox,oy)
	指定元素由參考點 2D 橫向移動 ox 距離、縱向移動 oy 距離，等於是結合 translateX(ox), translateY(oy) 。參數如果只指定 1 個，省略的第 2 個參數，會視為 0 ，也就是只有橫向移動。
	* matrix(a,b,c,d,e,f)
	指定元素由參考點依據數學變形矩陣 (transformation matrix) 的 6 個參數值產生 2D 變形。矩陣的目的主要在運算出四邊形四角的座標，屬於數學問題，這裡就不作太多討論了。事實上，前述的各項變形函數都是簡化這個矩陣而拆解出來的，稍後範例會看到對照。有一些線上工具可以比較容易幫我們產生這些參數值。

* ul li 橫向水平
	```
	li { display: inline-block; }
	```
* flex - 後面item往右靠  
	第一個item set "margin-right: auto"

---

*	function  
  *	calc()
  *	cubic-bezier(0.1, 0.7, 1.0, 0.1);

---

*	img 水平置中
	* margin: 0 auto - need set display = block
	```css
		width: 240px;		// set width
		margin: 0 auto
		display: block;	// set display = block
	```
* text 水平置中
	*	text-align: center

---

*	img 垂直置中
	* 添加偽元素 ( ::before、::after )  
	vertical-align: middle (在元素內的所有元素垂直位置互相置中，並不是相對於外框的高度垂直置中)  
	before 會造成前面有空格  

	```css
	.div0
	  width: 200px
	  height: 150px
	  border: 5px solid #000
	  &::after
	    content: ''
	    width: 0
	    height: 100%
	    display: inline-block
	    vertical-align: middle

	.redbox
	  width: 30px
	  height: 30px
	  background: #c00
	  display: inline-block
	  vertical-align: middle

  <div class="div0">
		<div class="redbox"></div>
	</div>
	```
	* calc 動態計算 - 要使用position relative 

	```css
	.div0
	  width: 200px
	  height: 150px
	  border: 1px solid blue

	.redbox
	  position: relative
	  width: 30px
	  height: 30px
	  background: #c00
	  top: calc(50% - 15px)
	  margin-left: calc(50% - 15px)
	```

	* transform - 要使用position relative 

	```css
	.div0
	  border: 1px solid blue
	  height: 100px
	  width: 200px

	.redbox
	  height: 30px
	  width: 30px
	  background: red
	  position: relative
	  margin: 0 auto
	  top: 50%
	  transform: translateY(-50%)

	<div class="div0">
		<div class="redbox"></div>
	</div>
	``` 

	*	絕對定位  
	將上下左右的數值都設為 0，再搭配一個margin:auto

	```css
	.div0
	  position: relative
	  width: 200px
	  height: 150px
	  border: 1px solid blue

	.redbox
	  position: absolute
	  width: 30px
	  height: 30px
	  margin: auto
	  top: 0
	  bottom: 0
	  left: 0
	  right: 0
	  background: #c00

	<div class="div0">
		<div class="redbox"></div>
	</div>	
	```

	*	使用 Flexbox  
	使用 align-items 或 align-content 的屬性，輕輕鬆鬆就可以做到垂直置中的效果喔  

	```css
	.div0
	  display: flex
	  width: 200px
	  height: 150px
	  border: 1px solid blue
	  justify-content : center
	  align-items : center    

	.redbox
	  width: 30px
	  height: 30px
	  background: #c00

	<div class="div0">
		<div class="redbox"></div>
	</div>	
	```


* text 垂直置中
	* 單行(僅對文字有效)  
		height: 400px  
		line-height: 400px (set as block height)

---

*	inline(內聯) 元素
	*	inline：span、strong、em
	*	inline-block：input、button、textarea、select、img

---

### special 
* vertical-align: middle (在元素內的所有元素垂直位置互相置中，並不是相對於外框的高度垂直置中)
* margin: 0 auto 僅對 block 有效,對 inline-block 無效
* text-align: center 對text都有效,但對其他僅 inline-block有效
* margin-top: 10% 是對照水平寬度

---

### vertical-align 常用參數表(配合display: table-cell)
  vertical-align:baseline;  預設值，元素在該行的基礎線上，大約在文字的中間位置，並不美觀。  
  vertical-align:sub; 圖片垂直對齊該行本文的下標位置。  
  vertical-align:super; 圖片垂直對齊該行本文的上標位置。  
  vertical-align:top; 圖片垂直對齊該行元素的最高位置。  
  vertical-align:text-top;  圖片垂直對齊該行文字的最高位置。  
  vertical-align:middle;  圖片垂直對齊該行文字的置中位置。  
  vertical-align:bottom;  圖片垂直對齊該行元素的最低位置。  
  vertical-align:text-bottom; 圖片垂直對齊該行文字的最低位置。  
  vertical-align:%; 以百分比來讓圖片垂直對齊該行文字，可以有負值。  

