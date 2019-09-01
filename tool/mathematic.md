<style>
.Maroon { 
color:Maroon; 
}
.Red { 
color:Red; 
}
.Orange { 
color:Orange; 
}
.Yellow { 
color:Yellow; 
}
.Olive { 
color:Olive; 
}
.Green { 
color:Green; 
}

.Purple { 
color:Purple; 
}

.Fuchsia { 
color:Fuchsia; 
}
.Lime { 
color:Lime; 
}
.Teal { 
color:Teal; 
}
.Aqua { 
color:Aqua; 
}
.Blue { 

color:Blue; 
}
.Navy { 
color:Navy; 
}

.Fb{
font-weight:bold;
}
</style>


# 數學

## 高斯函數
高斯函數符號 [x] 表示不大於 x 的最大整數

## 標準差
標準差應用於投資上，可作為量度回報穩定性的指標。標準差數值越大，代表回報遠離過去平均數值，回報較不穩定故風險越高。相反，標準差數值越小，代表回報較為穩定，風險亦較小。  
$\sqrt{mean(abs(x - x*mean())^2)}$  
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

## 積分  
$\int 2x+1 dx=x^2+x+C$  
求反導函數  
基本公式(不定積分 include C)  
> $\int x^r dx=\cfrac{1}{r+1}x^{r+1}+C$  
  $r!=-1$  
  故  $\int \cfrac{1}{x} dx$ 未知  

eg: 自由落體(為等加速運動)  
  $\cfrac{dx}{dt}=-9.8t$ (m/sec)  
  假設從 1000m 落下,求x(t)的高度(m)  
  x(10)的高度,幾秒落地  
> $x=\int \cfrac{dx}{dt}dt=\int -9.8t dt=-4.9t^2+1000$  
  x(100)=-490+1000=510 (m)  
  $-4.9t^2+1000=0$  
  $t^2=/cfrac {1000}{4.9}\approx 204$  
  $t\approx 14.3$ (sec)  

## (定)積分 --> 數
$\int^b_a f(x) dx$  f(x)對x從a到b的積分  

eg: $f(x)=\cfrac{dy}{dx}$ 速度  
> y=F(x) 是某一物體在時間x(sec)的位置(m)  
  $\cfrac{dy}{dx}=F'(x)=f(x)$ 速度(m/sec)  
  $\int^b_a f(x) dx$ 表從時間a 到時間 b 的位移  
  $=F(b)-F(a)$  
  ps: F(x)為f(x)的反導函數  

## 連續平均值  
$\mu=\cfrac{1}{b-a}\int^b_a f(x) dx$  

eg: $y=x^2$ x在0與2間的平均值  
> $\mu=\cfrac{1}{2-0}\int^2_0 x^2 dx$  
  $=[\cfrac{1}{2-0}\cfrac{1}{3}x^3]^2_0$  
  $=\cfrac{1}{2-0}\cfrac{8}{3}==\cfrac{4}{3}$  

eg: 平均成本 
成本模型 $C(t)=0.15t^2+0.2t+400$ (千元)  
t=0,1....24(月份) 求兩年平均成本  
> $\mu=\cfrac{1}{24-0}\int^{24}_0 0.15t^2+0.12t+400 dx$  
   $=\cfrac{1}{24-0}[0.15/3t^3+0.2/2t^2+400t]^{24}_0$
   $=\cfrac{1}{24-0}(10348.8-0)=431.2$  
* ... mask red line

## 一次估計
f(x) 在 a 點可得切線函數 y=mx+b  
若 x 接近於 a 可直接由 切線函數 算出值 

eg: 本金為P,年利率為r,一年k次計息,利率應為多少?  
> $P(1+x)^k=P(1+r)$  
  $(1+x)^k=(1+r)$  
  $x=\sqrt[k]{1+r}-1$ 太複雜了  
  求 $f(x)=(1+x)^k$ 切線函數 $f'(x)= k(x+1)^{k-1}$  
  (0,f(0))=(0,1)  
  f'(0)=k  
  $k=\cfrac{y-1}{x-0}$  
  切線方程式 y=kx+1  
  當 x 接近-->0  f(x)=f'(x)  
  $(1+x)^k=(1+r)=kx+1$  
  $x=\cfrac{r}{k}$  

## 連續微分(複利設為無限多期) 
$\lim\limits_{k \rightarrow \infty} (1+\cfrac{r}{k})^k$  
設 k=nr --> n=k/r , 若 $k \rightarrow \infty$ 則 $n \rightarrow \infty$  
> $\lim\limits_{k \rightarrow \infty} (1+\cfrac{r}{k})^k$  
  = $\lim\limits_{n \rightarrow \infty} (1+\cfrac{r}{nr})^{nr}$ 因 r為常數  
  = $(\lim\limits_{n \rightarrow \infty} (1+\cfrac{1}{n})^n)^r$ 因算出  $\lim\limits_{n \rightarrow \infty} (1+\cfrac{1}{n})^n$=e  
  = $e^r$  

eg:
> $[e^{2x}]'=e^{2x}[2x]'=2e^{2x}$  
  $[e^{x/3}]'=e^{x/3}[x/3]'=\cfrac{1}{3}e^{x/3}$  
  $[e^{-x^2}]'=e^{-x^2}[-x^2]'=-2xe^{-x^2}$  

## 自然數指數微分
已知 $[e^x]'=e^x$  
> $[e^u]'=[e^u]'u'$ 依連鎖率  
  $=u'e^u$ 因 $[e^x]'=e^x$ 故 $[e^u]'=e^u$  
  <b class="Blue">$[e^u]'=u'e^u$</b>  

## 標準指數的反導函數
已知 $\cfrac{d}{dx}[e^x]=e^x$ --> $\int e^xdx=e^x+C$  
定積分$\int^1_{-1} e^xdx=[e^x]^1_{-1}=e-\cfrac{1}{e}$  
$\int 3e^xdx=3\int e^xdx=3e^x+C$  

$\int e^{2x}dx$ (u=2x --> du=2dx) 
> = $\cfrac{1}{2}\int e^u du$  
  = $\cfrac{1}{2}e^u+C$  
  = $\cfrac{1}{2}e^{2x}+C$  

$\int e^x - e^{-x} dx$
> =$\int e^x dx - \int e^{-x} dx$  (-x=u du=-dx)  
  =$\int e^x dx + \int e^u du$  
  =$e^x$+$e^u+C$  
  =$e^x$+$e^{-x}+C$  

## 機率分布函數(正規分布,鐘形曲線)
f(x)>0 且 $\int^{\infty}_{-\infty} f(x) dx=1$  即為 機率分布曲線  
$y=n^{-x^2}$ n>0 都為鐘形曲線  
為方便計算取  $y=e^{-x^2}$   
計算鐘形曲線的積分要用平方才計算的出來  
$[\int^{\infty}_{-\infty} e^{-x^2} dx]^2$  
> = $[\int^{\infty}_{-\infty} e^{-x^2} dx]$ $[\int^{\infty}_{-\infty} e^{-x^2} dx]$  
  = $[\int^{\infty}_{-\infty} e^{-x^2} dx]$ $[\int^{\infty}_{-\infty} e^{-x^2} dy]$  
  = $\int^{\infty}_{-\infty} [\int^{\infty}_{-\infty} e^{-(x^2+y^2)} dxdy$  
  = 曲面 $z=e^{-(x^2+y^2)}$ 與 x y 平面的體積  
  旋轉體的薄殼積分  
  = $\int^\infty_0 2 \pi x e^{-x^2} dx$  
  $\int 2\pi x e^{-x^2} dx$ 令 $u=-x^2$ --> $du=-2x dx$  
  = $-\pi\int -2x e^u dx$  
  = $-\pi\int e^u du$  
  = $-\pi e^u+C$  
  = $-\pi e^{-x^2}+C$  
  $\int^\infty_0 2\pi x e^{-x^2} dx$  
  = $\lim\limits_{n \rightarrow \infty}[-\pi e^{-x^2}]^A_0$  
  = $\lim\limits_{n \rightarrow \infty}[-\pi e^{-A^2}-(-\pi)]$  
  = $\pi$  
  令 f(x)= $\cfrac{1}{\sqrt\pi}e^{-x^2}$  
  則 f(x)>0 $\int^\infty_{-\infty} f(x) dx=1$  
  f(x) 是一個 機率分布函數  

## 誤差函數(Error function) 唯一個 鐘形曲線  
$\int^\infty_{-\infty} e^{-x^2} dx=\sqrt\pi$  
> $\int^1_{-1} e^{-x^2} dx$  
  =$\cfrac{-\sqrt\pi erf(-1) + \sqrt\pi erf(1)}{2}$ or $\sqrt\pi erf(1)$  
  efr(x) = $\cfrac{2}{\sqrt\pi} \int^x_0 e^{-t^2} dt$
  $\int^1_{-1} e^{-x^2} dx$  
  =$2\int^1_{0} e^{-x^2} dx$  
  =$2\int^1_{0} e^{-t^2} dt$  
  =$\sqrt\pi \cfrac{2}{\sqrt\pi}\int^1_{0} e^{-t^2} dt$  
  =$\sqrt\pi erf(1)$  
  $\sqrt\pi erf(1)$ 大約 1.49..   

$\lim\limits_{x \rightarrow \infty} erf(x)$=$\cfrac{2}{\sqrt\pi} \int^\infty_0 e^{-x^2} dx=erf(\infty)$  
> $\cfrac{2}{\sqrt\pi} \int^\infty_0 e^{-x^2} dx$  
  = $\cfrac{2}{\sqrt\pi}(\cfrac{1}{2} \int^\infty_{-\infty} e^{-x^2} dx)$  
  = $\cfrac{2}{\sqrt\pi}(\cfrac{1}{2} \sqrt\pi)=1$  

## 自然對數之積分
ln(a)是自然指數, log(a)是常用指數  

已知 $[e^x]'=e^x$  其他 $2^x,3^x,4^x$...如何微分?  
對任意 a>0 存在 k ,使得 $e^k=a$, 也就是$e^k=a$有唯一解  

$a^x=(e^k)^x=e^{kx}$  --> $k=ln(a)$  
> $[a^x]'$=$[e^{kx}]'$
  =$[kx]'e^{kx}$ 因 <b class="Maroon">$[e^u]'=u'e^u$</b>  
  =$ke^{kx}$=$ka^x$ 因 <b class="Maroon">$k=ln(a)$</b>  
  = $ln(a) \cdot a^x$  
  <b class="Blue">$[a^x]'=ka^x=ln(a) \cdot a^x$</b> <b class="Blue">$a>0$</b>  

> $\sqrt2$ : 是 $x^2=2$ 的正數解  
  log2 : 是 $10^x=2$ 的解  
  ln2 : 是 $e^x=2$ 的解  


## 特殊函數  
erf(n) : 誤差函數(Error function)  

## 機率
* **機率分佈函數**
> 1. f(x)>=0  
  2. $\int^{\infty}_{-\infty} f(x) dx=1$  
* mask red line

## 指數
* **公式**  
> $a^{m+n}=a^m a^n$  
  $a^{m*n}=(a^m)^n$  
  $a^{m-n}=\cfrac{a^m}{a^n}$  
  $a^{-n/m}=\cfrac{1}{a^{n/m}}$  
  $a^{n/m}=(a^{1/m})^n$  
*** mask red line

eg:a^0 a!=0
> $a^0=a^{n-n}=\cfrac{a^n}{a^n}=1$  

eg:0^0 a!=0
> $a^0=0^{n-n}=\cfrac{0^n}{0^n}=\cfrac{0}{0}$  不討論  

eg: 2^{1.6}
> $2^{1.6}=2^{16/10}=2^{8/5}=(2^8)^{1/5}=\sqrt[5]{256}=3.03$  

## 對數  

* **常用對數公式**  
log(a \cdot b) = log(a)+log(b)  
log(a/b) = log(a)-log(b)  
$log(a^x)$ = $x \cdot log(a)$  

eg: $a^x=b$ 之解  
> $log(a^x)=log(b)$  
  x log(a)=log(b)  
  x=$\cfrac{log(b)}{log(a)}$  

* **自然對數公式**  
$ln(a \cdot b)$ = $ln(a)+ln(b)$  
$ln(a/b)$ = $ln(a)-ln(b)$  
$ln(a^x)$ = $x \cdot ln(a)$  

eg: a^x=b$ 之解
> ln $a^x$ = ln b  
  x$\cdot$ln a =ln b  
  x = $\cfrac{ln(b)}{ln(a)}$

$[log(x)]'=[\cfrac{ln(x)}{ln(10)}]'$  

## GeoGebra
高斯函數 : floor  
f'(x) : f(x) 微分  
x(A) : A點x座標  
|x| : 絕對值  
h2: x= 5 垂直線   
Integral[f(x)]:反導函數  
sqrt() : 開根號  \sqrt[3]{5} 
cbrt( ): 立方根  
Solve() : 求解 
abs() : 絕對值  
floor() : 小或等於之最大整數  
ceil() : 大或等於之最小整數  
round() : 四捨五入  
! : 階乘  
nroot(256,5) : 256 開 5 次方  


## doing
runing 35


## color select 
<table >
　<tr>
    <td class="Fb Maroon">Maroon</td>
    <td class="Fb Red">Red</td>
    <td class="Fb Orange">Orange</td>
    <td class="Fb Yellow">Yellow</td>
    <td class="Fb Olive">Olive</td> 
　</tr>
　<tr>
    <td class="Fb Green">Green</td>
    <td class="Fb Purple">Purple</td>
    <td class="Fb Fuchsia">Fuchsia</td>
    <td class="Fb Lime">Lime</td>
    <td class="Fb Teal">Teal</td>
　</tr>
  <tr>
    <td class="Fb Aqua">Aqua</td>
    <td class="Fb Blue">Blue</td>
    <td class="Fb Navy">Navy</td> 
  </tr>
</table>

```
<p>eg: show <b class="Maroon">Maroon</b>,<b class="Red">red</b>,<b class="Blue">blue</b>....</p>
```
<p>eg: show <b class="Maroon">Maroon</b>,<b class="Red">red</b>,<b class="Blue">blue</b>....</p>
