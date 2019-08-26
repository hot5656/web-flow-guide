
# 數學

## 高斯函數
高斯函數符號 [x] 表示不大於 x 的最大整數

## 標準差
標準差應用於投資上，可作為量度回報穩定性的指標。標準差數值越大，代表回報遠離過去平均數值，回報較不穩定故風險越高。相反，標準差數值越小，代表回報較為穩定，風險亦較小。  
$\sqrt(mean(abs(x - x*mean())^2))$  
(red mask only....) ***


# 微積分

## Note  
極限-->連續-->微分  
左極限/右極限 : 兩邊不相等,極限即不存在


## 極限定理(極限存在)
> Markdown Viewer set "MathJax on"  
> f(x)=L,g(x)=M  

$a. 常數函數 \lim\limits_{x \rightarrow a} (C)$  
$b. \lim\limits_{x \rightarrow a} (x)$  
$c. \lim\limits_{x \rightarrow a} [f(x)+g(x)]=L+M$ , $\lim\limits_{x \rightarrow a} [f(x)-g(x)]=L-M$  
$d. \lim\limits_{x \rightarrow a} [f(x)*g(x)]=L*M$  
$e. \lim\limits_{x \rightarrow a} [f(x)/g(x)]=L/M$
> g(x) != 0)  

$f. \lim\limits_{n \rightarrow a} f(x)^n=L^n$  
> n為正整數

$g. \lim\limits_{n \rightarrow a} \sqrt[n]{f(x)}=\sqrt[n]{L}$  
> n 為偶數,L>=0

## 連續函數的定義
$a. \lim\limits_{x \rightarrow a} f(x)存在$  
$b. f(a) 有意義$  
$c. \lim\limits_{x \rightarrow a} f(x) = f(a) $  

## 連續函數的定理
1. $f(x)=c$ 則在 x=a 連續  
2. $f(x)=x$ 則在 x=a 連續  
3. $f(x)=\sqrt{x}$ 則在 a=0 ~ $\infty$連續  

**f(x),g(x) 在  x=a 連續**  
4. $f(x)+g(x)$ 則在  x=a 連續, $f(x)-g(x)$ 則在  x=a 連續  
5. $f(x)*g(x)$ 則在  x=a 連續  
6. $f(x)/g(x)$ 若g(a)!=0 則在 x=a 連續  
> f(x)=多項式 --> 一定是連續函數  
  有理函數 $h(x)=f(x)/g(x)$ ,多項式 h(x) 在 x=a 連續 (if g(x)!=0) --> 一定是連續函數

## 切線-->點+斜率(變化率)  
斜率m=$\Delta y/\Delta x$  
    =$tan \theta$  
    =(y2-y1)/(x2-x1)  
    水平 m=0  
    垂直 m不存在
    正負決定m的方向,絕對值決定m的程度  
    切線可算出某x點y值-->算出切線方程式   
    切線存在的點,就是平滑的點  
f(x)在a點的導數(derviative)$ \lim\limits_{x \rightarrow a} (f(x)-f(a))/(x-a)$ 新符號為 f'(a)  
f(x) P(a,f(a)) 切線斜率 m=$ \lim\limits_{x \rightarrow a} (f(x)-f(a))/(x-a)$  
                        f'(a)=$ \lim\limits_{h \rightarrow 0} (f(a+h)-f(a))/h$  
                        導數公式f'(x)=$ \lim\limits_{h \rightarrow 0} (f(x+h)-f(x))/h$ 
												微分的符號  
												y'=f'(x)  
                        $\cfrac{dy}{dx}  = \cfrac{df(x)}{dx} = \cfrac{d}{dx}f(x)$ 

## 基本微分法
1. $\cfrac{d}{dx}c=0$  
2. $\cfrac{d}{dx}[cf(x)]=c\cfrac{df(x)}{dx}$  
3. $\cfrac{d}{dx}[f(x)+g(x)]=\cfrac{d}{dx}f(x)+\cfrac{d}{dx}g(x), \cfrac{d}{dx}[f(x)-g(x)]=\cfrac{d}{dx}f(x)-\cfrac{d}{dx}g(x)$  
4. $\cfrac{d}{dx}x=1$  
5. r:實數 $\cfrac{d}{dx}x^r=rx^{r-1}$  

## 乘法/除法微分
1. [f(x)g(x)]' = f'(x)g(x) + f(x)g'(x)  
> $\cfrac{d}{dx}[f(x)g(x)]=\cfrac{d}{dx}f(x)*g(x)+f(x)*\cfrac{d}{dx}g(x)$  
2. $[\cfrac{f(x)}{g(x)}]' = \cfrac{g(x)f'(x)-f(x)g'(x)}{[g(x)]^2}$  

## 連鎖率
(gof)(x) = g(f(x)), y=g(u) u=f(x)  
$\cfrac{dy}{dx} = \cfrac{dy}{du}\cfrac{du}{dx}$  
$[g(f(x))]'=\cfrac{dg(u)}{du}*\cfrac{df(x)}{dx}$  
(red mask only....) ***

## 高階導數
$f'(x)= \cfrac{dy}{dx} = \cfrac{df(x)}{dx}$ 一階導數  
$f''(x)= \cfrac{d^2y}{dx^2} = \cfrac{d^2f(x)}{dx^2}$ 二階導數  
$f^{(n)}(x)= \cfrac{d^ny}{dx^n} = \cfrac{d^nf(x)}{dx^n}$ n階導數  
> s(x) 距離  
> v(x) = s'(x) 速度  
> a(x) = s''(x) 加速度  

## 不可微函數
平滑可微  
ex:f(x)=|x| x=0 是否可微  
> $\lim\limits_{x \rightarrow a}f(x)$  
  $= \cfrac{f(x)-f(0)}{x-0}$  
  $= \cfrac{|x|}{x}$  
  $\lim\limits_{x \rightarrow a^+}\cfrac{|x|}{x}=1$  
  $\lim\limits_{x \rightarrow a^-}\cfrac{|x|}{x}=-1$  
  左極限!=右極限 極限不存在 所以在 x=0 點不可微

## 函數繪圖三部曲 
1. 漸進線   $$y=f(x) \space x\rightarrow \infty \space or \space y\rightarrow \infty$$
> $f(x)=\frac{1}{x^t}$ t>0 --> $\lim\limits_{x \rightarrow \infty} \frac{1}{x^t}=0$  
  $\lim\limits_{x \rightarrow \infty} \frac{x^3+2x+6}{7x^3+4x^2-8x+19}$
  = $\lim\limits_{x \rightarrow \infty} \frac{\frac{x^3}{x^3} + \frac{2x}{x^3} + \frac{6}{x^3}}{ \frac{7x^3}{x^3}+ \frac{4x^2}{x^3}- \frac{8x}{x^3}+ \frac{19}{x^3}}$
  = $\lim\limits_{x \rightarrow \infty} \frac{1 + \frac{2}{x^2} + \frac{6}{x^3}}{ 7+ \frac{4}{x}- \frac{8}{x^2}+ \frac{19}{x^3}}$ = $\frac{1}{7}$  
  or $\lim\limits_{x \rightarrow \infty}x^3$  遠大於 $\lim\limits_{x \rightarrow \infty}x^2$  所以
  $\lim\limits_{x \rightarrow \infty} \frac{x^3+2x+6}{7x^3+4x^2-8x+19}$
  = $\lim\limits_{x \rightarrow \infty} \frac{x^3}{7x^3}$ = $\lim\limits_{x \rightarrow \infty} \frac{1}{7}$ = $\frac{1}{7}$  

$\lim\limits_{x \rightarrow \infty} f(x)=b$ y=b 為 y=f(x) 之 水平漸近線 ex:f(x)=1/x, f(x)=(2x-3)/(3x+6)  
$\lim\limits_{x \rightarrow a} f(x)=\infty$ x=a 為 $f(a)=\infty$ 之 x=a 為垂直漸近線 ex:$f(x)=1/x^2, f(x)=1/(fx-3)^3$  
> $f(x)=\cfrac{x^2-4x}{x^2-4x+3}$  
  $x \rightarrow +\infty,-\infty \space y=1$ 水平漸近線  
  $y \rightarrow 1^-, y \rightarrow -\infty; ,y \rightarrow 1^+, y \rightarrow \infty$ 垂直漸近線  
  $y \rightarrow 3^-, y \rightarrow \infty; ,y \rightarrow 3^+, y \rightarrow -\infty$ 垂直漸近線  


2. 局部極值-相對極值  $$f'(x)$$
相對極小/大值

3. 反曲線(微調)-臨界點  $$f''(x)$$
f(x) f(c)=0 or f'(c)不存在 --> (c,f(c)) 為 f(x) 之臨界點(critical point)  
ex:$f(x)=x^{\cfrac{2}{3}}+1$
> f'(x)=$\cfrac{2}{3}x^{\cfrac{-1}{3}}$ =$\cfrac{2}{3x^{\cfrac{1}{3}}}$  
  $x(-\infty,0)$, f'(x)<0 --->  $f(x)\searrow$  
  $x(0,\infty)$, f'(x)>0 --->  $f(x)\nearrow$  
  (0,f(0)) 為相對極小值   

## 遞增/遞減函數 
$遞增函數(f(x)\nearrow)$ x1 > x2  --> f(x1) > f(x2)  
> f'(a)>0 f(x) 在 a 點為 遞增  
  故 x屬於I區間 f'(x)>0 --> $f(x)\nearrow$  
     x屬於I區間 f'(x)<0 --> $f(x)\searrow$  
     x屬於I區間 f'(x)=0 --> f(x)=c  

$遞減函數(f(x)\searrow)$ x1 < x2  --> f(x1) < f(x2)  

ex: $f(x)=x^2$  
> f'(x)=2x  
  $x(-\infty,0)$, f'(x)<0 --->  $f(x)\searrow$  
  $x(0,\infty)$, f'(x)>0 --->  $f(x)\nearrow$  

ex: $f(x)=x^2+2x+5$  
> f'(x)=2x+2=2(x+1)  
  f'(-1)=0  
  $x(-\infty,-1)$, f'(x)<0 --->  $f(x)\searrow$  
  $x(-1,\infty)$, f'(x)>0 --->  $f(x)\nearrow$  

ex: $f(x)=x^3$  
> $f'(x)=3x^2$  
  f'(-1)=0  
  $x(-\infty,0)$, f'(x)>0 --->  $f(x)\nearrow$  
  $x(0,\infty)$, f'(x)>0 --->  $f(x)\nearrow$  

## 函數繪圖
ex: $(fx)=\cfrac{x}{x^2-1}$  
> 漸進線 $x \rightarrow \infty$  
  $\lim\limits_{x \rightarrow \infty}(fx)=\cfrac{x}{x^2-1}=0$  
  $\lim\limits_{x \rightarrow -\infty}(fx)=\cfrac{x}{x^2-1}=0$  
  --> y=0 有水平漸進線  
  漸進線 y $\rightarrow \infty$  
  $(fx)=\cfrac{x}{x^2-1}$
  =$\cfrac{x}{(x+1)(x-1)}$  
  x=-1  
  $\lim\limits_{x \rightarrow -1^-}\cfrac{x}{(x+1)(x-1)}=-\infty$  
  $\lim\limits_{x \rightarrow -1^+}\cfrac{x}{(x+1)(x-1)}=\infty$  
  x=1  
  $\lim\limits_{x \rightarrow 1^-}\cfrac{x}{(x+1)(x-1)}=-\infty$  
  $\lim\limits_{x \rightarrow 1^+}\cfrac{x}{(x+1)(x-1)}=+\infty$  
  相對極植  
  $(fx)=\cfrac{x}{x^2-1}$  
  $f'(x) = \cfrac{(x^-1)-x 2x)}{(x^2-1)^2}$  
  $=\cfrac{-x^2-1}{(x^2-1)^2}$  
  $=\cfrac{-(x^2+1)}{((x+1)(x-1))^2}$  
  不可能 f'(x)=0  
  x=1,-1 微分不存在 --> 不是臨界點因不在原函數定義域內  

ex: $(fx)=\cfrac{1}{x^2+1}$  
> 漸進線 $x \rightarrow \infty$    
  $\lim\limits_{x \rightarrow \infty}(fx)=\cfrac{1}{x^2+1}=0$  
  $\lim\limits_{x \rightarrow -\infty}(fx)=\cfrac{1}{x^2+1}=0$  
  --> y=0 有水平漸進線  
  $x^2+1$ 永遠不等於0,故無垂直漸進線  
  相對極植  
  $(fx)=\cfrac{1}{x^2+1}$  
  $f'(x) = \cfrac{-2x}{(x^2+1)^2}$  
  x=0 為臨界點  
  $x(-\infty,0)$, f'(x)>0 --->  $f(x)\nearrow$  
  $x(0,\infty)$, f'(x)<0 --->  $f(x)\searrow$  
  (0,f(0))=(0,1) 為相對極大值  

ex: $(fx)=x^3$  
> 漸進線 $x \rightarrow \infty$    
  $\lim\limits_{x \rightarrow \infty}(fx)=x^3=\infty$  
  $\lim\limits_{x \rightarrow -\infty}(fx)=x^3=-\infty$  
  --> 無水平漸進線  
  相對極植  
  $(fx)=x^3$  
  $f'(x)=3x^2$  
  x=0 為臨界點  
  $x(-\infty,0)$, f'(x)>0 --->  $f(x)\nearrow$  
  $x(0,\infty)$, f'(x)>0 --->  $f(x)\nearrow$  
  --> x=0 無極值  

求反曲點  
f''(x)=6x  

|----|$(-\infty,0)$|$x(0,\infty)$  |  
|------|:------------:      |:-------:         |  
|  f'' | -                  |+                 |  
|  f'  |  $f(x)\searrow$    | $f(x)\nearrow$   |  
|  f   |凹向下(concave down)|凹向上(concave up)|  
f(0)=0 所以反曲點為 (0,0)  


ex: $(fx)=x^4-2x^2+2$  
> 漸進線 $x \rightarrow \infty$  
  $\lim\limits_{x \rightarrow \infty}(fx)=\lim\limits_{x \rightarrow -\infty}(fx)=\infty$  
  漸進線 y $\rightarrow \infty$  
  $f'(x)=4x^3-4x=4x(x^2-1)=4(x+1)(x)(x-1)$  
  x=-1,0,1 可能有極值

----|$(-\infty,-1)$|(-1,0)|(0,1)|$x(1,\infty)$
----|:------------:      |:-------:         |:-------:         |:-------:
f'  |-    |+   |-   |+
f   |$\searrow$ |$\nearrow$|$\searrow$|$\nearrow$
-->(-1,0):極小值,(0,2):極大值,(1,1):極小值

> 求反曲點  
  $f''(x)=12x^2-4=12(x^2-\cfrac{1}{3})= 12(x+\cfrac{1}{\sqrt{3}})(x-\cfrac{1}{\sqrt{3}})$  
  $x=-\cfrac{1}{\sqrt{3}},\cfrac{1}{\sqrt{3}}$ 有反曲點  

---|$(-\infty,-\cfrac{1}{\sqrt{3}})$|$(-\cfrac{1}{\sqrt{3}},\cfrac{1}{\sqrt{3}})$|$x(\cfrac{1}{\sqrt{3}},\infty)$
---|:------------:    |:--:                |:-------:
f''|+                 |-                   |+                 
f' |$f(x)\nearrow$    |$f(x)\searrow$      |$f(x)\nearrow$
f  |凹向上(concave up)|凹向下(concave down)|凹向上(concave up)



## 反曲點
定理-設 y=f(x)定義在(a,b)開區間  
> a. (a,b)區間 ,f''(x)>0 --> f(x)圖形凹向上(concave up)  
  b. (a,b)區間 ,f''(x)<0 --> f(x)圖形凹向下(concave down)  

定理 (c,f(c))為圖形凹性改變之處, -->(c,f(c)) 稱為函數f(x)之反曲點  
> f''(c)=0 or f''(c) 不存在 有可能有反曲點  

ex: $f(x)= x^4-2x^3-12x^2+12x+1$
> $f'(x)=4x^3-6x^2-24x+12$  
  $f''(x)=12x^2-12x-24=12(x^2-x-2)$  
  =12(x+1)(x-2)=0  
--> x=-1 or x=2 可能有反曲點  

|----  |$(-\infty,-1)$|(-1,2)|$x(2,\infty)$                       |  
|------|:------------:    |:--:                |:-------:         |  
|  f'' |+                 |-                   |+                 |  
|  f'  |$f(x)\nearrow$    |$f(x)\searrow$      | $f(x)\nearrow$   |  
|  f   |凹向上(concave up)|凹向下(concave down)|凹向上(concave up)|  
(-1,f(-1)=(-1,-20),(2,f(2))=(2,-23)為反曲點  

## 極值 二階導數判別法
定理
> 設 f''(x) 在 (a,b) 存在 x=c 為 f(x)之臨界點(極值)  
  a. 若 f''(c)<0 --> f(x) 在 x=c 有相對及大值  
  b. 若 f''(c)>0 --> f(x) 在 x=c 有相對及小值  
  c. 若 f''(c)=0 --> 無法判斷  

eg: $f(x)=\cfrac{1}{x}+x$
> $f'(x)=\cfrac{-1}{x^2}+1$=$\cfrac{x^2-1}{x^2}$=$\cfrac{(x+1)(x-1)}{x^2}$  
  ==>x=1,x=-1可能有極值(x=0 不在定義域 故不用考慮)  
  $f''(x)=2x^-3=\cfrac{2}{x^3}$  
  $f''(-1)=-2 <0 --> 相對極大$  
  $f''(1)=2 >0  --> 相對極小$  

## 絕對極值  
關心: 1. [a,b] 2. 連續函數  
定理 
> 若 f(x)為定義在[a,b]閉區間的連續函數
  則存在c,d 在 [a,b]之間  
  f(c)為絕對極大  
  f(d)為絕對極小  
  考慮臨界點 or 端點  

eg: $f(x)=x^2$ 在[-2,3] 之絕對極值  
> f'(x)=2x=0  
  臨界點 x=0  
  端點 x=-2,3  
  f(0)=0 --> 絕對極小  
  f(-2)=4  
  f(3)=9 --> 絕對極大  

## GeoGebra
高斯函數 : floor  
x(A) : A點x座標  
|x| : 絕對值  
h2: x= 5 垂直線   
Integral[f(x)]:反導函數  

## doing
runing 35

