# CSS record

*   [Root](../README.md)
*   [1. font-size](#a1)
*   [2. flex](#a2)


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
	default order value is 0
	order: -1;
	```
*	align-self : auto | flex-start | flex-end | center | baseline | stretch
		```
		對單一item
		```



