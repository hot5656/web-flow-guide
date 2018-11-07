SS record

*   [Root](../README.md)
*   [1. font-size](#a1)
*   [2. flex](#a2)
*   [3. 中文直排](#a3)
*   [4. sector](#a4)
*   [5. grid](#a5)
*   [6. susy 3](#a6)


<h2 id="a1">1. font-size</h2>

```
//default font-size=16px

//em
文字單位 em 是相對的的數值單位，它會受到外圍的文字大小所影響，而 1em 即是 1 的文字大小， 1.5em 也就是 1.5 倍的文字大小

//rem
rem 也是相對的文字尺寸，和 em 使用方法接近，不同的是他僅相對於 root 層級的文字大小(網頁中的 html)
```

<h2 id="a2">2. flex</h2>

[reference](https://wcc723.github.io/css/2017/07/21/css-flex/)  
[reference2](https://cythilya.github.io/2017/04/06/flexbox-advance/)
### Flex 外容器屬性
*	display : flex / inline-flex
	```
	inline-flex，作用類似於 inline-block + flex
	```
*	flex-flow
	*	flex-direction : row | row-reverse | column | column-reverse; 
		```
		排列方向
		```
  *	flex-wrap : nowrap | wrap | wrap-reverse; 
  	```
  	超過是否換行
  	nowrap 超過不換行
  	wrap-reverse 換行時反轉
  	```
*	justify-content : flex-start | flex-end | center | space-between | space-around;
		```
		主軸的設定是上方的 flex-direction；所以實際是水平(row)或垂直(column)，要依主軸的方向而定
		flex-start : 靠前
		flex-end :　靠後
		center : 靠中間
		space-between : 間隔平均放中間
		space-around : 間隔平均放於中間和兩邊
		```
*	align-items : flex-start | flex-end | center | baseline | stretch;
		```
		相對於上一個屬性，這是交錯軸的對齊設定
		flex-start : 靠前
		flex-end :　靠後
		center : 靠中間
		baseline : 位於容器之基線(可能是中間)
		stretch : 默認值(可能是開頭)
		```
* align-content : flex-start | flex-end | center | space-between | space-around | stretch;
	```
	align-items 的多行版本
	```

### Flex 內元件屬性
*	flex
	*	flex-grow : 元件的伸展性(佔幾份)，是一個數值，當空間分配還有剩餘時的當前元件的伸展性，預設值為 0，如果設置為 0 則不會縮放。
	```
	default order value is 0
	flex-grow: 1;
	flex-grow: 2;
	```
	*	flex-shrink : 元件的收縮性(空間不夠時佔幾份)元件的伸展性，是一個數值，當空間分配還不足時的當前元件的收縮性，預設值為 0，如果設置為 0 則不會縮放。
	```
	default order value is 0
	flex-shrink: 1 ;
	flex-shrink: 2 ;
	```
	*	flex-basis : 元件的基準值，可使用不同的單位值
	```
	flex-basis: 50px;
	```
*	order
	```
	default order value is 0(定義element可改變位置)
	order: -1;
	```
*	align-self : auto | flex-start | flex-end | center | baseline | stretch
		```
		對單一item
		```

<h2 id="a3">3. 中文直排</h2>

```
// 由右至左
writing-mode: vertical-rl;

// 由左至右
writing-mode: vertical-lr;
```


<h2 id="a4">4. sector</h2>

```
.a1 : class = a1
#a2 : id = a2
* : all element
p : <p> element
div, p : all element <div> and <p>
div p : <div> 內的 <p>
div > p : parent 為 <div> 的 <p>
div + p : 緊跟在 <div> 後的 <p>  ??? not work chrome
p ~ ul  : <p> 之前的 <ul>
[target] : element 含有 attribute 為 target
[target=_blank] : element 含有 attribute 為 target=_blank
[title~=flower] : title attribute 含有 string flower
[lang|=en] : lang attribute value 開頭為 en
a[href^="https"] : a element attribute href 開頭為 "https"
a[href$=".pdf"] :  a element attribute href 結束為 ".pdf"
a[href*="w3schools"] :  a element attribute href 包含有 "w3schools"
p::before : p元素之前生成、插入的內容適用的選擇器。偽元素
p::after  : 緊跟p元素之後生成、插入的內容適用的選擇器。偽元素

	
```

<h2 id="a5">5. grid</h2>

[reference](https://wcc723.github.io/css/2017/03/22/css-grid-layout/)
### 外部容器
*	display: grid | inline-grid | subgrid  
	分別由 column 及 row 定義出直排與橫列的格線，內容再依隔線作安排
*	grid-template-rows: < track-size > ... | < line-name > < track-size > ...;  
	track-size: 可使用彈性的長度、百分比或分數 (分數的部分需使用 fr 單位)
	fr 單位就是為了格線布局而生  
	
	line-name: 可自行命名的名稱  
	``` CSS
	.wrapper {
	  display: grid;
	  grid-template-columns: [main-start] 1fr [content-start] 1fr [content-end] 1fr [main-end];
	  grid-template-rows: [main-start] 100px [content-start] 100px [content-end] 100px [main-end];
	}
	```
*	grid-template-columns: < track-size > ... | < line-name > < track-size > ...;  

	example :  
	```
	.wrap {
	  display: grid;
	  grid-template-columns: 200px 50px auto 50px 200px;
	  grid-template-rows: 25% 100px auto;
	  grid-template-areas:
    	"header header header header header"
    	"side  main main main main"
    	"side footer footer footer footer";

	  height: 100vh;
	  width: 940px;
	  margin: 0 auto;
	}
	.item-a {
	  grid-area: header;
	  background-color: purple;
	}
	.item-b {
	  grid-area: main;
	  background-color: orange;
	}
	.item-c {
	  grid-area: side;
	  background-color: green;
	}
	.item-d {
	  grid-area: footer;
	  background-color: gray;
	}
	.wrap {
		grid-template-columns: repeat(2, 1fr 2fr) 100px;  
		/* grid-template-columns: repeat({次數}, {格線...} | {格線...}) | {格線...}; */
	}
	```
* grid-template: 60% 40% / 200px auto; --> row column
*	grid-column-gap: 10px; /* 設定左右間距 */
*	grid-row-gap: 20px; /* 設定上下間距 */
	* grid-column-gap 以及 grid-row-gap 可以合併為 grid-gap：  
		grid-gap: 20px 10px;
	*	可以用grid-auto-rows設定 auto-height 的最小高度
* order: 排列順序,如z-index可為負值
	```css
	.water {
	  order: 0;
	}
	#poison {
	order: -1
	}
	```
* grid-auto-columns: 60px;
*	grid-auto-flow
	```
	grid-auto-flow: row | column | row dense | column dense
	```
*	justify-items, justify-content, align-content --> 與 flex 的使用方法一樣

### 內部容器
*	grid-column-start: 2; column start 位置(from 1,也接受負值)
*	grid-column-end: 5; column end 位置(opsition not include)
	* grid-column-start: span 3(include block)
	* grid-column-end: span 2(include block)
	*	grid-column: 4 / 6 --> include start and end
*	grid-row-start: 3
	* grid-row: 3/6 --> include start and end
*	grid-area --> grid-row-start/ grid-column-start/ grid-row-end/grid-column-end.
	* grid-area: 1/2/4/6
* justify-self, align-self -->  與 flex 的使用方法一樣


<h2 id="a6">6. susy 3</h2>

[susy doc](http://oddbird.net/susy/docs/)  
[example1](https://codepen.io/yisenliu/pen/wqevwR)  
[example2](https://codepen.io/qtgye/pen/VWxrVQ)
[example3](https://codepen.io/mirisuzanne/pen/VWzwXj)
*	 box-model setting a global box-sizing
	```scss
	// import susy
	@import "../node_modules/susy/sass/susy";
	@import "../node_modules/susy/sass/plugins/svg-grid";

	// Settings
	$susy: (
		'columns': susy-repeat(8),	// 幾格
		//'columns': 1 1 2 2 1 1 2 2,	// 幾格
		//'columns': susy-repeat(6, 180px), // 6格 180px - gutter auto count
		//'columns': 120px susy-repeat(4) 120px, // 6column include 2 120px - gutter auto count
		'svg-grid-colors': hsla(180, 50%, 50%, 0.25),	// 測試格顏色
		//'gutters': 1/3,	// 間隔(1/3:相對格寬, %:相對vw, 1em,  )
		//'spread': 'wider'  // every element extend gutter : narrow (none), wide (one), or wider (two)
		//'container-spread':  'wider' // 增加最前及的後 guttter :　narrow (none), wide (one), or wider (two)
	);

	// box-sizing
	* { box-sizing: border-box; }
	```

