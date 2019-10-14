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

## 無序清單(* + -)-same
```
* 1st
	* the 1-1
	* the 1-2
	+ the 1-3
	- the 1-4
```
* 1st
	* the 1-1
	* the 1-2
	+ the 1-3
	- the 1-4

## 有序清單
```
1. Yahoo 股市 
2. Yahoo!奇摩股市
```
1. Yahoo 股市 
2. Yahoo!奇摩股市

## 超連結
```html
[goole](https://www.google.com/ "Google")
<!-- md link to id-->
[Django project](#django_project)  
<a id="django_ref"></a>
<!-- md link to top-->
[[Home]](#)
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

```
|預設|靠右對齊|靠左對齊|置中對齊|
|---|------:|:-----|:-----:|
|12 |12     |12    |12     |
|123|123    |123   |123    |
|1  |1      |1     |1      |
```
|預設|靠右對齊|靠左對齊|置中對齊|
|---|------:|:-----|:-----:|
|12 |12     |12    |12     |
|123|123    |123   |123    |
|1  |1      |1     |1      |

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

## 水平分隔線
```
第一個水平分隔線：
***
第二個水平分隔線：
---
第三個水平分隔線：
___
```
第一個水平分隔線：
***
第二個水平分隔線：
---
第三個水平分隔線：
___

## 數學公式
```
# 行內公式
質能方程式$E = mc^2$
# 獨立公式
質能方程式$$E = mc^2$$
# ^ 上標, _ 下標
$$x = a _{1}^n + a_ {2}^n + a_{3}^n$$
# 分數使用\frac{分母}{分子} 不過推薦使用\cfrac來代替\frac，顯示公式不會太擠
$$\frac{1}{3} 與\cfrac{1}{3}$$
# {}因為有特殊作用因此當需要顯示大括號時一般使用\lbrace \rbrace來表示
$$f(x, y) = 100 * \lbrace[(x + y) * 3] - 5\rbrace$$
# 開根號 \sqrt[次数]{被开方数}
$$\sqrt[3]{X} \sqrt{5 - x}$$ 
# 極限
$g. \lim\limits_{n \rightarrow a} [f(x)/g(x)]=L/M$
# 條件表達式
\[
y=
\begin{cases}
-x,\quad x\leq 0 \\
x,\quad x>0
\end{cases}
\]
\begin{equation}
    f(n) =
    \begin{cases}
    n/2, & \text{if $n$ is even} \\
    3n+1, & \text{if $n$ is odd}
    \end{cases}
\end{equation}
```
質能方程式$E = mc^2$  
質能方程式$$E = mc^2$$  
上標,下標  
$$x = a _{1}^n + a_ {2}^n + a_{3}^n$$  
分數使用  
$$\frac{1}{3} 與\cfrac{1}{3}$$  
開根號  
$$f(x, y) = 100 * \lbrace[(x + y) * 3] - 5\rbrace$$  
$$\frac{1}{3} 與\cfrac{1}{3}$$  
$$\sqrt[3]{X} \sqrt{5 - x}$$  
極限  
$\lim\limits_{n \rightarrow a} [f(x)/g(x)]=L/M$
條件表達式  
\[
y=
\begin{cases}
-x,\quad x\leq 0 \\
x,\quad x>0
\end{cases}
\]
\begin{equation}
    f(n) =
    \begin{cases}
    n/2, & \text{if $n$ is even} \\
    3n+1, & \text{if $n$ is odd}
    \end{cases}
\end{equation}

**希臘字母**

代碼          |大寫 |代碼 |小寫
--------------|-----|-----|----
A		|$A$		|\alpha		|$\alpha$
B		|$B$		|\beta		|$\beta$ 
\Gamma	|$\Gamma$	|\gamma		|$\gamma$ 
\Delta	|$\Delta$	|\delta		|$\delta$
E		|$E$		|\epsilon	|$\epsilon$
Z		|$Z$		|\zeta		|$\zeta$
H		|$H$		|\eta		|$\eta$
\Theta	|$\Theta$	|\theta		|$\theta$
I		|$I$		|\iota		|$\iota$
K		|$K$		|\kappa		|$\kappa$
\Lambda	|$\Lambda$	|\lambda	|$\lambda$
M		|$M$		|\mu		|$\mu$
N		|$N$		|\nu		|$\nu$
\Xi		|$\Xi$		|\xi		|$\xi$
O		|$O$		|\omicron	|$\omicron$
\Pi		|$\Pi$		|\pi		|$\pi$
P		|$P$		|\rho		|$\rho$
\Sigma	|$\Sigma$	|\sigma		|$\sigma$
T		|$T$		|\tau		|$\tau$
\Upsilon|$\Upsilon$	|\upsilon	|$\upsilon$
\Phi	|$\Phi$		|\phi		|$\phi$
X		|$X$		|\chi		|$\chi$
\Psi	|$\Psi$		|\psi		|$\psi$
\Omega	|$\Omega$	|\omega		|$\omega$


**關係運算符**

符號		|代碼
--------	|---
$\pm$		|\pm
$\times$	|\times
$\div$		|\div
$\mid$		|\mid
$\nmid$		|\nmid
$\cdot$		|\cdot
$\circ$		|\circ
$\ast$		|\ast
$\bigodot$	|\bigodot
$\bigotimes$|\bigotimes
$\bigoplus$	|\bigoplus
$\leq$		|\leq
$\geq$		|\geq
$\neq$		|\neq
$\approx$	|\approx
$\equiv$	|\equiv
$\sum$		|\sum
$\prod$		|\prod
$\coprod$	|\coprod

**集合運算符**

符號		|代碼
--------	|---
$\emptyset$	|\emptyset
$\in$		|\in
$\notin$	|\notin
$\subset$	|\subset
$\supset$	|\supset
$\subseteq$	|\subseteq
$\supseteq$	|\supseteq
$\bigcap$	|\bigcap
$\bigcup$	|\bigcup
$\bigvee$	|\bigvee
$\bigwedge$	|\bigwedge
$\biguplus$	|\biguplus
$\bigsqcup$	|\bigsqcup

**對數運算符**

符號	|代碼
--------|---
$\log$	|\log
$\lg$	|\lg
$\ln$	|\ln

**三角運算符**

符號	|代碼
--------|---
$\bot$	|\bot
$\angle$|\angle
$\sin$	|\sin
$\cos$	|\cos
$\tan$	|\tan
$\cot$	|\cot
$\sec$	|\sec
$\csc$	|\csc

**微積分運算符**

符號		|代碼
--------	|---
$\prime$	|\prime
$\int$		|\int
$\iint$		|\iint
$\iiint$	|\iiint
$\iiiint$	|\iiiint
$\oint$		|\oint
$\lim$		|\lim
$\infty$	|\infty
$\nabla$	|\nabla
$\mathrm{d}$|\mathrm{d}

**其他**

符號		|代碼
--------	|---
$\rightarrow$  |\rightarrow
$\uparrow$  |\uparrow
$\nearrow$  |\nearrow
$\searrow$  |\searrow
普通空格$\space$空格|\space 
字符空格$\quad$空格 |\quad
$\cdot$		|\cdot
$\approx$ |\approx
顯示公式較好看$\displaystyle \sum_{n=1}^{10} n^2$ |\displaystyle "\displaystyle \sum_{n=1}^{10} n^2"
$\overline{x+1}$|\overline 能覆蓋所有括號中的文本
$\bar x$        |\bar 長度只能覆蓋一個字母
$\displaystyle \sum_{i=1}^n$  |\sum_{i=1}^n 總和
$\frac{1}{3}$  |\frac{1}{3}
$\sqrt[3]{X}$  |\sqrt[3]{X}
$\sqrt{5 - x}$ |\sqrt{5 - x}
$\int^1_{-1}$  |\int^1_{-1}
$\pm$					 |\pm
$\lim\limits_{n \rightarrow \infty}$  |\lim\limits_{n \rightarrow \infty}
\begin{cases} -x,\quad x\leq 0 \\x,\quad x>0 \end{cases}|


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










