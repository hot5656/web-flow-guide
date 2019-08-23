
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
  $x \rightarrow +\infty,-\infty \space y=1$  
  $y \rightarrow 1^-, y \rightarrow -\infty; ,y \rightarrow 1^+, y \rightarrow \infty$  
  $y \rightarrow 3^-, y \rightarrow \infty; ,y \rightarrow 3^+, y \rightarrow -\infty$  


2. 局部極值  $$f'(x)$$


3. 反曲線(微調)  $$f''(x)$$


## GeoGebra
高斯函數 : floor  
x(A) : A點x座標  
|x| : 絕對值  

## doing
複習小測驗15-4

