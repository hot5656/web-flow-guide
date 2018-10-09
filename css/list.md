# Css List

*   [Root](../README.md)

### < ul >
  no icon - list-style-type: none; 
  水平 display:inline;
### < a >
  無底線 text-decoration: none;
### < img > 
  垂直置中 : vertical-align:middle;
  clip-path: inset(10% 0 10% 0);
  ---- need set inline-block ,width and height
  background-size: cover;
  background-position: center center;
  background-image: url("../../img/photo-1473256599800-b48c7c88cd7e.jpg");
### 文字
  水平置中 text-align:center;(display: block;)
  垂直置中 line-height as parents height
### box-sizing
  box size 不受 padding and border 影響
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

### other
	img:first-child  由 parent 眼光看(first-child)
