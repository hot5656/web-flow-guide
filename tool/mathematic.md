
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
f'(x) $\cfrac{dy}{dx} = \cfrac{df(x)}{dx}$ 一階導數  
f''(x) $\cfrac{d^2y}{dx^2} = \cfrac{d^2f(x)}{dx^2}$ 二階導數  
$f^{(n)}$ $\cfrac{d^ny}{dx^n} = \cfrac{d^nf(x)}{dx^n}$ n階導數  
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


## GeoGebra
高斯函數 : floor

