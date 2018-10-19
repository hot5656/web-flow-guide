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
  *	clip-path: inset(10% 0 10% 0);  
  *	need set inline-block ,width and height  
  background-size: cover;  
  background-position: center center;  
  background-image: url("../../img/photo-1473256599800-b48c7c88cd7e.jpg");  
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
*	function  
  *	calc()
  *	cubic-bezier(0.1, 0.7, 1.0, 0.1);





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

