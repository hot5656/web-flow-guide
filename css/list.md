# Css List

*   [Root](../README.md)

*	write css
	* inline sheet
	```
	<div style="background-color:#000; color:#fff;>Test</div>
	``` 

	*	internal sheet
	```
	<style>
	body {
		color: blue;
	}
	</style>
	```

	* external sheet 
	```
	<link rel="stylesheet" href="all.css">
	```

*	css variable 
	```
	// define 
	:root {
		--circle-width: 100px;
	}
	// HTML
	<div id="circle"></div>
	// use variable
	#circle	{
		width: var(--circle-width);
		height: var(--circle-width);
		border-radius: 50%;
		background-color: pink;
	}	
	```

*	sector
	```
	body { ...}
	.myId { ... }
	#testClass { ... }
	[lang=my] { ... }// attribute
	[href] { ... }
	```

*	html attribute vs css property

*	 !important 
	```css
	 p { color: blue !important; }
	```

* browser Prefix(for olld browser)
	```
	-ms- for Microsoft Internet Explorer
	-moz- for Mozilla Firefox
	-o- for Opera
	-webkit- for Chrome and Safari(iOS)
	```

*	style link
	```
	// LoVe/HAte rule
	// visited 僅在清除 cash 才會清除
	:link --> :visited --> :hover --> :active
	a:link {
	　//設定還沒瀏覽過的連結樣式
	}
	a:visited {
	　//設定已經瀏覽過的連結樣式
	}
	a:hover {
	　//設定滑鼠移到連結上的樣式
	}
	a:active {
	　//設定正在被點選的連結樣式
	}
	// example
	a:link {
		color: blue;
	}
	a:visited {
		color: red;
	}
	a:hover {
		color: green;
	}
	a:active {
		color: yellow;
	}
	```

*	other 
	```
	color:
	font-size:
	background-color: red;
	padding/padding-top/padding-bottom/padding-left/padding-right
	margin/margin-top/margin-bottom/marin-left/margin-right
		px,em.cm...
		margin: 10px 0 10px 85%
	width 
	max-width
		% (parent)
		auto(default)
		px,cm,em
		100wh
	height
	min-height
		% (parent) - not every browser support well
		auto(default)
		px,cm,em
		100vh
	border
		border-width
			px
		border-color
		border-style
			none
			solid : normal
			dotted : 點
			ridge : 3D 立體浮凸框
			inset : 凹框
			double : double solid
			groove : 3D 立體內凸框
			outset : 凸框
			dashed : 虛線
		border-left-width
		border-right
	cursor
		url : image
		auto : I 字
		crosshair : 十字
		default
		e-resise : <-->
		help : default + ?
		move : <--> +^ + v
		n-resize : ^+|+v
		ne-resize : 右斜 ^+|+v
		nw-resize : 左斜 ^+|+v
		pointer : 手
		progress : default + 圓圈轉
		s-resize : some same as n-resize
		se-resize : some same as nw-resize
		sw-resize : some same as ne-resize
		text : | 輸入文字
		w-resize : some same as e-resize
		wait : 圓圈轉
		inherit
	display :
		none :hide
		block : all line
		inline : 
		inline-block : inline can set width
	visibility
		visible (default)
		hidden
		collapse
		initial
		inherit
		--------------
		inline-tabel :
		list-item
		table
		table-caption
		table cell
		tabel-column
		table-row
		inherit
	max-width
	min-width
	max-height
	min-height
		none (no max-width, not applicable min-width)
		%
		px,xm,em..;
	position
		static (default) 
		absolute
			top
			left
			bottom
			right
		relative : move offset 
			top
			left
			bottom
			right
		fixed (reference browser windows)
			top
			left
			bottom
			right
		inherit (follow parent)
	z-index : 
		large value put top(absolute)
		default value is 0
		auto (default and same as parent)
		+ or - value
	float 
		left : move left as it can
		right : move right as it can
		inherit 
		none
	clear (not float left or right)
		none
		left : not allow left
		right : not allow right
		both : not allow both
		inherit
	vertical-align : 以用來設計網頁中圖片在垂直方向的對齊方式
		sub : 圖片垂直對齊該行本文的下標位置
		super : 圖片垂直對齊該行本文的上標位置
		baseline : 元素在該行的基礎線上 (default)
		top : 圖片垂直對齊該行元素的最高位置
		text-top : 圖片垂直對齊該行文字的最高位置
		bottom : 圖片垂直對齊該行文字的置中位置
		text-bottom : 圖片垂直對齊該行元素的最低位置
		middle : 圖片垂直對齊該行文字的置中位置
		% : 以百分比來讓圖片垂直對齊該行文字，可以有負值。
		inherit :
	background-position ( for Sprite - 圖片合併)
	opacity : 透明效果(0.8),1不透明
	// inline tag
		<a href=""></a>
		<em></em> : marks text that has stress emphasis which traditionally means that the text is displayed in italics by the browser. This tag is also commonly referred to as the <em> element.
		<span></span>
		<img src="" alt="">
	// block tag
		<div></div>
		h1~h6
		<ol><ul><li>
		<pre> : pre 元素可定義預格式化的文本。被包圍在pre 元素中的文本通常會保留空格和換行符。而文本也會呈現為等寬字體。
					pre 標籤的一個常見應用就是用來表示計算機的源代碼。
		<blockquote> 標籤可定義一個塊引用,所有文本都會從常規文本中分離出來，經常會在左、右兩邊進行縮進，而且有時會使用斜體。也就是說，塊引用擁有它們自己的空間。
	// Pseudo
	:first-child - 1st item
		div > u:first-child {border: 1px solid black;}
	:first-letter - 1st letter
		p:first-letter {font-size: 32px;}
	:first-line - 1st line
		body:first-line {word-spacing: 15px;}
	:focus - input click
	:lang
		// can not have space
		// some use for language detect , ex. lang(en)
		div:lang(i-am-waesome) {bord: 1px sold red;} 
		<div lang="i-am-waesome">Vordered, I am!</div>
	:before
		strong:before { content: "NOTICE: ";}
	:after 
		span:after { content: " Writeen by me!";}
	> - 接續 element
	```

* css Sprite - 圖片合併
	```
	// 合併的圖檔
	1. enter --> https://spritegen.website-performance.org/
	2. clear - remove default .png
	3. open - select icon png
	4. setting
		can select layout : compact/vertical/horizontal
	5. download
		png --> spritesheet : download png
		png --> stylesheet  : css class
	6. check  download --> HTML for example using
	// example css
	.sprite {
	    background-image: url(spritesheet.png); 
	    background-repeat: no-repeat;
	    display: inline-block;
	}
	.sprite-approval {
	    width: 32px;
	    height: 32px;
	    background-position: -5px -5px;
	}

	.sprite-company {
	    width: 32px;
	    height: 32px;
	    background-position: -47px -5px;
	}

	.sprite-conference {
	    width: 32px;
	    height: 32px;
	    background-position: -89px -5px;
	}

	.sprite-curriculum {
	    width: 32px;
	    height: 32px;
	    background-position: -5px -47px;
	}

	.sprite-headhunting {
	    width: 32px;
	    height: 32px;
	    background-position: -47px -47px;
	}

	.sprite-hiring {
	    width: 32px;
	    height: 32px;
	    background-position: -89px -47px;
	}

	.sprite-interview {
	    width: 32px;
	    height: 32px;
	    background-position: -5px -89px;
	}

	.sprite-meeting {
	    width: 32px;
	    height: 32px;
	    background-position: -47px -89px;
	}

	.sprite-punctuality {
	    width: 32px;
	    height: 32px;
	    background-position: -89px -89px;
	}

	.sprite-question {
	    width: 32px;
	    height: 32px;
	    background-position: -131px -5px;
	}

	.sprite-rating {
	    width: 32px;
	    height: 32px;
	    background-position: -131px -47px;
	}

	.sprite-team {
	    width: 32px;
	    height: 32px;
	    background-position: -131px -89px;
	}
	// example HTML
	<i class="sprite sprite-approval"></i>
	<i class="sprite sprite-company"></i>
	<div>Test1<i class="sprite sprite-approval"></i></div>
	<div>Test2<i class="sprite sprite-company"></i></div>
	// background-position 
	top/right : +x +y
	bottom/right : +x -y
	bottom/left : -x -y (站在顯示element立場看,利用這個)
	top/left : -x +y
	```

*	position
	```css
	// css 
		// 對所有元素
		p:nth-child(odd) {
			background-color: pink;
		}
		// 僅對P元素
		p:nth-of-type(odd) {
			color: blue;
		}	
	// html
		<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nisi, praesentium.</p>
		<hr>
		<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nisi, praesentium.</p>
		<hr>
		<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nisi, praesentium.</p>
		<hr>
		<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nisi, praesentium.</p>
		<hr>
		<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nisi, praesentium.</p>
		<hr>
		<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nisi, praesentium.</p>
	```
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
	// position: 3(from 1)
	&:nth-child(3)
		margin-right: 0px
	// position: 3,6,9...
	&:nth-child(3n)
		margin-right: 0px
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
  *	background-image: url("../../img/photo-1473256599800-b48c7c88cd7e.jpg");  
		```css
		// url("floe.pgn") , none , inherit
		background-repeat: 
			no-repeat 背景圖案不重複
			repeat-x 背景圖案在 x-方向重複
			repeat-y 背景圖案在 y-方向重複
			repeat  背景圖案在 x- 及 y-方向重複(default)
			inherit : inherit parent element
		background-attachment: 
			fixed 背景圖案永遠是停留
			scroll 背景圖案將與捲動的動作一起移動-ex. page down(default)
			inherit : 
		background-position: [left,center,right,%(靠左百分比,0:由左方開始顯示),y position] [top,center,bottom,%(靠上百分比,0:由上方開始顯示),x position] 
			-->1st x, 2nd y 
		background-size：bg-size(寬度,%是表示對容器百分比,auto對應比例自動調整), bg-size(高度,%是表示對容器百分比,auto對應比例自動調整)
			auto(預設值)	即背景圖片原始長寬
			length 				指定圖片具體大小的數值，不允許負值(當只設定一個數值，另一個數值預設值為auto)
			percentage		以背景圖所在元素的百分比指定背景圖大小，不允許負值(
			cover					主要用於背景圖小於所在的內容，此時就可以採用cover的方式，使背景圖放大至內容的大小，但此方法容易使背景圖因放大而失真
			contain				主要用於背景圖大於所在內容，但卻需要將背景圖完整呈現，此時就可採用contain的方式，使背景圖縮小至內容的大小。
		// 常用 image 
			background-size: cover
		```


  *	white-space: 空白的處理方法  
    normal(default)   連續的空白字都縮減為一個空白，長行遇到右邊界會跳行分為兩行 
    nowrap 連續的空白字會縮減為一個空白，不跳行  
  *	text-indent 首行  
     text-indent : 36px 首行縮排  
     text-indent : -36px 首行凸出來

*	text
  *	水平置中 text-align:center;(display: block;)  
		```
		center (x-axis)
		justify : 使左右對齊本文
		inherit
		left
		right
		```
  *	垂直置中 line-height as parents height  
  *	height: 50px  
  * font-size  
  	16px
  	inherit
  	em
  	rem
  *	line-height: 50px  
  *	text-align: center  
  *	letter-spacing: 1px; 字間隔
  *	text-decoration 
	  none        : 預設值，不顯示任何文字特效  
	  overline    : 替文字增加上線  
	  underline   : 替文字增加底線  
	  line-through: 替文字增加刪除線  
	  blink       : 替文字增加閃爍效果，已取消  
	  inherit     : 繼承自父層的文字效果  (default)
	*	font-weight  
		inherit (default)
		normal - 這是預設值，可以不用設定。  
		bold - 粗體字。  
		bolder - 更粗的字型，不過用起來跟 bold 似乎沒什麼差異。  
		lighter - 細體，不過與 normal 沒什麼差異。  
		數字 - 可以設定的有 100、200、300、400、500、600、700、800、900。  
	* font-style 屬性是用來設定字體是否為斜體字 (italic 或 oblique)
		italic (italic)
		inherit (default)
		none (link italic)
		oblique
	*	text-indent (縮排)
	```
		inherit 
		px
		% of parent
	```
	*	font-family : 字體的類別 verdana,arial,impact(有space要以雙引號標示)
	* text-overflow(css3)
		```css
		clip : 超過截掉
		ellipsis : 超過 show ...
		// example 
		<div style="border: 1px solid black; width:100px; white-space: nowrap; overflow: hidden; text-overflow: clip;">
			This is a really long sentence
		</div>
		<div style="border: 1px solid black; width:100px; white-space: nowrap; overflow: hidden; text-overflow: ellipsis;">
			This is a really long sentence
		</div>
		```
	* text-transform
			capitalize : 1st letter to capital
			lowercase : lowercase letter
			uppercase : uppercase
			none 
	*	overflow
		```
		auto //預設會自動使用捲軸
		visible  //顯示的文字或圖片會直接超出範圍，不使用捲軸。
		hidden   //自動隱藏超出的文字或圖片
		scroll   //自動產生捲軸(若不需要也會產生垂直卷軸)
		inherit  //繼承自父元素
		-------------
		othet
		overflow-x : hidden
		overflow-y: auto
		```
	*	white-space
		```
		normal // 連續的空白字元會被合併(collapse)
		nowrap // 對待空白字元的方式跟 normal 一樣，且會強制不換行
		pre    // 連續的空白字元都會被保留。換行在有換行字元以及<br>時發生
		pre-wrap // 連續的空白字元都會被保留。換行會在換行字元、有<br>元素以及被文字空間限制時發生
		pre-line // 連續的空白字元會被合併(collapse)。換行在換行字元、 <br>以及被文字空間限制時發生
		```
	* word-spacing 單字（或段落）水平距離
	* letter-spacing 文字水平方向間的空白區間(可為負值)
		normal (default)
		px,em...
		inherit (not all browser support)

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
	// example 
		transition: filter 3s, box-shadow 3s 2s
	// --
	.box  
		height: 50px 
		width: 50px 
		transition: all 1s 
		&:hover 
			width: 300px
	```
	*	只對單一屬性加入 transition  (all 會較浪費時間)
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
	* translate(ox,oy) - 移至座標(ox,oy)
	指定元素由參考點 2D 橫向移動 ox 距離、縱向移動 oy 距離，等於是結合 translateX(ox), translateY(oy) 。參數如果只指定 1 個，省略的第 2 個參數，會視為 0 ，也就是只有橫向移動。
	transform:translate(180px) rotate(-5deg) scale(0.8);
	* matrix(a,b,c,d,e,f)
	指定元素由參考點依據數學變形矩陣 (transformation matrix) 的 6 個參數值產生 2D 變形。矩陣的目的主要在運算出四邊形四角的座標，屬於數學問題，這裡就不作太多討論了。事實上，前述的各項變形函數都是簡化這個矩陣而拆解出來的，稍後範例會看到對照。有一些線上工具可以比較容易幫我們產生這些參數值。
	
* input 
	*	placeholder color
	```css
  ::placeholder
  	color: $c-info
	```


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
	* margin: 0 auto - need set display = block(相對的寬度應為固定)
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


### 字體 font-family)
* 泛用字 generic-family

```
serif 明體(襯線體)
sans-serif 黑體(無襯線體)
cursive 捲曲字體
fantasy 花俏字體
monospace 等寬字體
```

* 指定字體 family-name

```
Helvetica (Mac內建,無襯線字體一種)
Times (Mac內建,襯線字體一種)
PingFang TC (Mac內建,繁中字體)
Helvetica Neue(新版 Helvetica)

Arial (microsoft內建,無襯線字體一種,近似於 Helvetica) 
Times New Roman (microsoft內建,襯線字體一種)
Microsoft JhengHei (microsoft內建 微軟正黑體)
MingLiU (細明體字型)
PMingLiU (新細明體字型)

SemiBold (思源宋體)-Google/Adobe
```

* 字重(weight)

```css
css
font-weight: normal|bold|bolder|lighter|number|initial|inherit
normal	Defines normal characters. This is default
bold	  Defines thick characters
bolder	Defines thicker characters
lighter	Defines lighter characters
100~900
initial	Sets this property to its default value.
inherit	Inherits this property from its parent element.

是指相對於字高度的筆畫粗細(stroke width),一個字體（typeface）的某個字型(font)的字重常常至少4-6個,其中正常與黑體幾乎是必備的
	100 - 淡體 Thin ( Hairline )
	200 - 特細 Extra-light ( ultra-light )
	300 - 細體 Light
	350 - 次細 Demi-Light
	400 - 標準 Regular ( normal / book / plain )
	500 - 適中 Medium
	600 - 次粗 Demi-bold/semi-bold
	700 - 粗體 Bold
	800 - 特粗 Extra-bold/extra
	900 - 濃體 Black(Heavy)
	950 - 特濃 Extra-black(Ultra-black)
```

* example

```css
$font-title: 'PingFang TC','Microsoft JhengHei',sans-serif;
$font-normal: 'Helvetica Neue',Arial,serif;
$font-times: Times,'Times New Roma',serif;

$weight-bold: bold;
$weight-normal: normal;
$weight-light: lighter; 

font-family: $font-title
font-weight: $weight-bold
```

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

### css3
*	Border radius
	```
	border-radius: 10px; (0r %)
	border-radius: 10px 0 20px 10px;
	border-top-left-radius
	border-top-right-radius
	border-bottom-left-radius
	border-bottom-right-radius
	```

* Border image
	```
	border-image: source slice width outset repeat|initial|inherit;
		border-image: url("/images/border.png") 30 30 repeat;
	border-image-source 圖片來源網址。
	border-image-slice 將要使用的圖片邊框分割為九格，分別抓出四個角的圖片。
		/* 所有的边 */
		border-image-slice: 30%; 
		/* 垂直方向 | 水平方向 */
		border-image-slice: 10% 30%;
		/* 顶部 | 垂直方向 | 底部 */
		border-image-slice: 30 30% 45;
		/* 上 右 下 左 */
		border-image-slice: 7 12 14 5; 
		/* 使用fill（fill可以放在任意位置） */
		border-image-slice: 10% fill 7 12;
		/* Global values */
		border-image-slice: inherit;
		border-image-slice: initial;
		border-image-slice: unset;
	border-image-width 設定圖片邊框的寬度。
	border-image-outset 邊框圖片超出邊框的量。
	border-image-repeat 設定圖片的填滿方式，有三種常用參數。
		round - 用重複方式填滿，有縮放圖片功能*。(當不能整數次平舖時，根據情況放大或縮小圖像)
		repeat - 用重複方式填滿。
		stretch - 用延展方式填滿。
		space - 用重複方式填滿(當不能整數次平舖時，會用空白間隙填充在圖像周圍)
	// css 
		.b-border {
			width:330px;
			height: 200px;
			border:20px solid transparent;
			border-image:url("border.png") 27 round;
	  /*border-image-source: url("border.png") ;
			border-image-slice: 27;
			border-image-width: 40px;
			border-image-outset: 20px;
			border-image-repeat: round;*/
		}
	// html
		<div class="b-border">Test border image</div>
	```

* Box shdow

	```
	box-shadow : horisontal-shadow vertical-shadow *blur *spread *color *insert/outset
		horisontal-shadow x-axis
		vertical-shadow y-axis
		blur(how much 模糊)
		spread(how much 延伸)
		color(default black)
		inset/outset(default)
	// example 
	.box {
		height: 100px;
		width: 100px;
		background-color: red;
		box-shadow: 10px 10px 25px 10px blue inset;
	}
	<div class="box"></div>
	```

* Filter 

```
grayscale灰階
sepia懷舊
saturate飽和
hue-rotate色相旋轉
invert負片
opacity不透明
brightness亮度
contrast對比
blur模糊
drop-shadow下拉陰影
/* <filter-function> values */
filter: blur(5px);
filter: brightness(0.4);
filter: contrast(200%);
filter: drop-shadow(16px 16px 20px blue);
filter: grayscale(50%);
filter: hue-rotate(90deg);
filter: invert(75%);
filter: opacity(25%);
filter: saturate(30%);
filter: sepia(60%);

/* Multiple filters */
filter: contrast(175%) brightness(3%);

/* Use no filter */
filter: none;

/* Global values */
filter: inherit;
filter: initial;
filter: unset;
```


*	Background Size

	```
	// use uwit backfround-image 
	background-size: 40px 40px
	background-size: 200% 200%
	background-size: contain (for all container for width)
	background-size: cover ( for width/height more)
	// example
	.contain1 {
		width: 100px;
		height: 200px;
		background-image: url("approval.png");
		background-repeat: no-repeat;
		background-size: contain;
		border: 1px solid red;
	}
	```

* Text shadow

	```
	text-shadow:horizontal-shadow vertical-shadow *blur *color
	horizontal-shadow  x-axis
	vertical-shadow y-axis
	blur (how much 模糊)
	color(default black)
	// example
	.text {
		font-size: 36px;
		text-shadow: 2px 2px 10px blue;
	}
	<div class="text">Test Shadow</div>
	```

* Custom Fonts
	
	```
	// 可指定網路字型 or user design 字型
	@font-face {
	  font-family: MyHelvetica;
	  src: local("Helvetica Neue Bold"),
	    local("HelveticaNeue-Bold"),
	    url(MgOpenModernaBold.ttf);
	  font-weight: bold;
	}
	p { font-family: MyHelvetica, serif; }
	```

* Rotate Element
	
	```
	transform: rotate(15deg);
	transform: rotate(-15deg);
	// example 
	.text {
		font-size: 36px;
		transform: rotate(15deg);
		border: 1px solid red;
		width: 200px;
	}
	<div class="text">Test Shadow</div>
	```

* Resize (not support very well)

	```
	// 要加入 overflow:auto; 才可 work
	resize
		horizontal
		vertical
		both
		none(default)
	// example 
	.text {
		font-size: 36px;
		border: 1px solid red;
		width: 200px;
		resize: both;
		overflow:auto;
	}
	<div class="text">Test Shadow</div>
	```

* will-change
	```
	css3 新增了一個屬性為 will-change，這個屬性用於提示瀏覽器此元素可能有 CSS 的改變(如：transition、transform等等)，讓瀏覽器可以針對 CSS 改變先做處理
		1. 不要將多個元素都設上 will-change，這樣瀏覽器會嘗試優化所有元素而消耗過多的機器資源，進而使網頁變得更慢。
		2. 在適當的時機加上 will-change。若我們一開始就在 stylesheet 對元素加上 will-change ，會導致瀏覽器一直對此元素做優化而消耗資源，我們應該適時的使用 script 等方式適當的加入、移除 will-change 屬性。
		3. 若網頁已非常順暢，就不要再多加 will-change，過多的 will-change 反而會造成記憶體的消耗及衍生效能問題。
		4. 給予足夠時間預先加入 will-change 屬性
	// 當 btn 點擊後改變透明度
	.btn { opacity: 0.5; } 
	.btn { will-change: opacity; }
	.btn:active { opacity: 0.8; }
	// 滑鼠移至按鈕時改變
	.btn { opacity: 0.5; }
	.container:hover > .btn { will-change: opacity; }
	.btn:hover { opacity: 0.8; }
	// --> 我們也可以使用 javascript 去動態加入及移除 will-change 屬性
畢竟，大多數的改變通常是有事件觸發
	```