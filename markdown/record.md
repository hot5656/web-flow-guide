# Markdown record
*   [Root](../README.md)

## 標題 1~6 
```
#  A
## A1
### A23
```
#  A
## A1
### A23


## 粗體/強調
```
**asdfasf**
asdfasf
*asdfasf* 
asdfasf
```
**asdfasf**
asdfasf
*asdfasf*
asdfasf

## 刪除
```
~~wqfwa~~
```
~~wqfwa~~

## 加背景色
```
`abd`
```
`abd`

## 特殊字元
```
< &lt;
& &amp;
```
&lt;  
&amp;

## 換行
```
行尾加上兩個以上的空白，然後按enter
```

## 分隔線
```
***
```
***

## 清單+分層
```
* Yahoo!奇摩股市提供您當日行情、大盤走勢、類股走勢、期貨及
	* 選擇權分類報價、港滬深股、美股、財經新聞等資訊。
		* 財經新聞等資訊。

*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
    viverra nec, fringilla in, laoreet vitae, risus.
<br>	
	Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
    viverra nec, fringilla in, laoreet vitae, risus.
*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
viverra nec, fringilla in, laoreet vitae, risus.
    > This is a blockquote
    > inside a list item.
```
* Yahoo!奇摩股市提供您當日行情、大盤走勢、類股走勢、期貨及
	* 選擇權分類報價、港滬深股、美股、財經新聞等資訊。
		* 財經新聞等資訊。

*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
    viverra nec, fringilla in, laoreet vitae, risus.
<br>
	Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
    viverra nec, fringilla in, laoreet vitae, risus.
*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
viverra nec, fringilla in, laoreet vitae, risus.
	``` javascript
	var a = 2;
	console.log()
	```
    > This is a blockquote  
    > inside a list item.
	``` javascript
	var a = 2;
	console.log()
	```

## 有序清單
```
1. Yahoo 股市 
2. Yahoo!奇摩股市
```
1. Yahoo 股市 
2. Yahoo!奇摩股市

## 超連結
```
[goole](https://www.google.com/ "Google")
```
[goole](https://www.google.com/ "Google")

## 圖片
```
![flower](flower.jpeg "pic title")
```
![flower](flower.jpeg "pic title")

## 表格
表格的欄位數以標題列的欄位數作為基準，有少則補。有多的，PHP 是直接判斷為文字，GFM 則是隱藏。  
分隔列每欄至少要有三個 - (dash)，可在 - 的最左最右插入 : 指定文字對齊方式， : 也算在最少三個 - 的數量裡  
欄位以 | (pipe) 劃分，表格外側可有可不有，但若只有單一欄位，則每欄至少要有一個 |  
欄位裡，文字與 | 之間的空白符號對程式來說無意義，但對於編寫者能加強可讀性。
```
|奇摩股市提供您當|大盤走勢、類股走及|選擇權分|
|--|:--:|--:|
|abc|def|123|
|eeeeee|eeee|21312|

Age           | Time  | Food | Gold | Requirement
--------------|:-----:|-----:| ----:|------------------------
Feudal Age    | 02:10 |  500 |    0 | Dark Age building x 2
Castle Age    | 02:40 |  800 |  200 | Feudal Age building x 2
Imperial Age  | 03:30 | 1000 |  800 | Castle Age building x 2 
```
|奇摩股市提供您當|大盤走勢、類股走及|選擇權分|
|--|:--:|--:|
|abc|def|123|
|eeeeee|eeee|21312|

Age           | Time  | Food | Gold | Requirement
--------------|:-----:|-----:| ----:|------------------------
Feudal Age    | 02:10 |  500 |    0 | Dark Age building x 2
Castle Age    | 02:40 |  800 |  200 | Feudal Age building x 2
Imperial Age  | 03:30 | 1000 |  800 | Castle Age building x 2 

## 區塊元素(程式碼)
``` javascript
var a = 2;
console.log()
```

## 區塊引言
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
> 
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.

## 區塊引言(階層)
> This is the first level of quoting.
>
> > This is nested blockquote.
>
> > > Back to the first level.

## 引言的區塊內也可以使用其他的Markdown語法，包括標題、清單、程式碼區塊等：
> ## This is a header.
> 
> 1. This is the first list item.
> 2. This is the second list item.
> 
> Here's some example code:
> ```
>     return shell_exec("echo $input | $markdown_script");
> ```

## 自動連結
```
<http://example.com/>  
<address@example.com>
```
<http://example.com/>  
<address@example.com>

## 跳脫字元
```
Markdown可以利用反斜線來插入一些在語法中有其他意義的符號，例如：如果你想要用星號加在文字旁邊的方式來做出強調效果（但不用<em>標籤），你可以在星號的前面加上反斜線：
\*literal asterisks\*
```
\*literal asterisks\*

Markdown支援在下面這些符號前面加上反斜線來幫助插入普通的符號：
```
\   反斜線
`   反引號
*   星號
_   底線
{}  大括號
[]  方括號
()  括號
#   井字號
+   加號
-   減號
.   英文句點
!   驚嘆號
```










