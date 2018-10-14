# Css List

*   [Root](../README.md)

### bloak
  border: 5px solid red 
  dorder: none
### < ul >
  no icon - list-style-type: none;  
  水平 display:inline;   
  --- list-style-type  
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
### < a >
  無底線 text-decoration: none;  
  &:hover
### < img > 
  垂直置中 : vertical-align:middle;  
  clip-path: inset(10% 0 10% 0);  
  ---- need set inline-block ,width and height  
  background-size: cover;  
  background-position: center center;  
  background-image: url("../../img/photo-1473256599800-b48c7c88cd7e.jpg");  
  ---- white-space: 空白的處理方法  
    normal(default)   連續的空白字都縮減為一個空白，長行遇到右邊界會跳行分為兩行 
    nowrap 連續的空白字會縮減為一個空白，不跳行  
  ---- text-indent 首行  
     text-indent : 36px 首行縮排  
     text-indent : -36px 首行凸出來  
### text
  水平置中 text-align:center;(display: block;)  
  垂直置中 line-height as parents height  
  height: 50px  
  line-height: 50px  
  text-align: center  
  letter-spacing: 1px; 字間隔
### box-sizing
  --- box size 不受 padding and border 影響  ---  
  box-sizing: border-box;  
### function
  calc()




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

### text-decoration 
  none        : 預設值，不顯示任何文字特效  
  overline    : 替文字增加上線  
  underline   : 替文字增加底線  
  line-through: 替文字增加刪除線  
  blink       : 替文字增加閃爍效果，已取消  
  inherit     : 繼承自父層的文字效果  

### other
	img:first-child  由 parent 眼光看(first-child)
