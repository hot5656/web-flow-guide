# phython record

*   [Root](../README.md)

## reference 
* **Machine Learning**  

涉及機率論、統計學、逼近論、凸分析、計算複雜性理論
> 機器學習想做的事情，簡單的說是要從資料中歸納出有用的規則。大數據說的是對大量的資料做分析，而人工智能說的是讓機器看起來更聰明，兩者都可以使用機器學習來做核心的工具  

監督式學習supervised learning(給予數據和標籤讓機器去學習)  
> 一個監督式學習者的任務在觀察完一些訓練範例（輸入和預期輸出）後，去預測這個函數對任何可能出現的輸入的值的輸出。  
  監督式學習就像是我們給了機器一堆貓的照片告訴機器說「這個是貓」，再給機器一堆狗的照片告訴它「這是狗」，讓機器自己去學習分辨，接著我們便能給予任何貓或狗的照片問機器讓機器告訴我們這是 貓 或 狗？

非監督式學習unsupervised learning(只給予數據沒有給予標籤)  
> 非監督式學習是一種機器學習的方式，並不需要人力來輸入標籤。它是監督式學習和強化學習等策略之外的一種選擇。在監督式學習中，典型的任務是分類和迴歸分析，且需要使用到人工預先準備好的範例(base)  
  非監督式學習就像是我們給了機器一堆貓的照片和一堆狗的照片，可是我們並沒有告訴機器說哪些是貓哪些是狗，要機器自己去學習判斷出分類出圖片的不同之處。

半監督式學習semi-supervised learning(結合監督式和非監督式)  
> 少部分資料有標準答案，可提供機器學習輸出時判斷誤差使用；大部分資料沒有標準答案，機器必須自己尋找答案。  
  我們任意選100張貓或狗的照片，在其中的10張告訴機器哪些是貓，哪些是狗，讓機器去學習認識貓與狗的外觀，再自己嘗試把另外90張照片內的特徵取出來進行分類。

增強學習(透過環境和經驗修正)  
> 人類在進行決策時，常常會根據目前「環境」 的「狀態」執行「動作」，執行動作會造成兩個結果：一是人們會得到「環境」給我們的回饋，也就是人類會得到「報酬」，接著我們所執行的動作也會去改變「環境」，使得「環境」進入到一個新的「狀態」，「觀察到目前的狀態->執行動作->收到報酬與觀察到新的狀態」的步驟，重複非常非常多次，直到某個終止時間。  
  和前面三種類型不同的地方在於，增強學習並不是一次給予全部資料先讓機器分類，而是不斷餵給機器資料，透過經驗讓機器不斷修正。



# Install package

## 1. install by pipe

* **upgrade pip**

```
python -m pip install --upgrade pip
```

* **jupyter notebook**

coding tool
```
pip install jupyter notebook
```

* **Python Requests**

對網路發動請求的套件，可實作對網頁做get、post等HTTP協定的行為
```
pip install requests
```

* **Python Beautifulsoup4**

借助網頁的結構特性來解析網頁的工具，只需要簡單的幾條指令就可以提取HTML標籤裡的元素
```
pip install beautifulsoup4
```

## 2. install in linux

* **python3**

```
// check install
apt list --installed | grep phython

// check version
python3 --version
```

* **Anaconda**

```
// web side
https://www.anaconda.com/distribution/

// get Bash script
cd temp
curl -O https://repo.anaconda.com/archive/Anaconda3-2019.07-Linux-x86_64.sh
// verify (md5 count)
md5sum Anaconda3-2019.07-Linux-x86_64.sh
// bash run
bash Anaconda3-2019.07-Linux-x86_64.sh
	...
	Do you approve the license terms? [yes|no] --> yes

	...
	[/home/sammy/anaconda3] >>>

	....
	Preparing transaction: done
	Executing transaction: \ WARNING conda.core.envs_manager:register_env(46): Unable to register environment. Path not writable or missing.
	  environment location: /home/robert/anaconda3
	  registry file: /home/robert/.conda/environments.txt
	done
	installation finished.
	Do you wish the installer to initialize Anaconda3
	by running conda init? [yes|no]
	[no] >>> --> yes
	no change     /home/robert/anaconda3/condabin/conda
	no change     /home/robert/anaconda3/bin/conda
	no change     /home/robert/anaconda3/bin/conda-env
	no change     /home/robert/anaconda3/bin/activate
	no change     /home/robert/anaconda3/bin/deactivate
	no change     /home/robert/anaconda3/etc/profile.d/conda.sh
	no change     /home/robert/anaconda3/etc/fish/conf.d/conda.fish
	no change     /home/robert/anaconda3/shell/condabin/Conda.psm1
	no change     /home/robert/anaconda3/shell/condabin/conda-hook.ps1
	no change     /home/robert/anaconda3/lib/python3.7/site-packages/xontrib/conda.xsh
	no change     /home/robert/anaconda3/etc/profile.d/conda.csh
	modified      /home/robert/.bashrc
	==> For changes to take effect, close and re-open your current shell. <==
	If you'd prefer that conda's base environment not be activated on startup, 
	   set the auto_activate_base parameter to false: 
	conda config --set auto_activate_base false
	Thank you for installing Anaconda3!
	===========================================================================
	Anaconda and JetBrains are working together to bring you Anaconda-powered
	environments tightly integrated in the PyCharm IDE.


// ==== just for reference ===
// 設置Anaconda環境
// conda create命令創建Anaconda環境。 例如，可以使用以下命令創建名為my_env的Python 3環境
conda create --name my_env python=3
// 激活新環境
source activate my_env
// =============================

// show token
jupyter notebook list  
```

* **crontab(環型工作排程)-linux comman**

|代表意義|分鐘|小時|日期|月份|週|指令|
|--------|----|----|----|----|---|----------|
|數字範圍|0-59|0-23|1-31|1-12|0-7|呀就指令啊|

特殊字符|代表意義
--------|----
*(星號)|代表任何時刻都接受的意思！舉例來說，範例一內那個日、月、週都是 * ， 就代表著『不論何月、何日的禮拜幾的 12:00 都執行後續指令』的意思！
,(逗號)|代表分隔時段的意思。舉例來說，如果要下達的工作是 3:00 與 6:00 時，就會是： 0 3,6 * * * command 時間參數還是有五欄，不過第二欄是 3,6 ，代表 3 與 6 都適用！
-(減號)|	代表一段時間範圍內，舉例來說， 8 點到 12 點之間的每小時的 20 分都進行一項工作： 20 8-12 * * * command 仔細看到第二欄變成 8-12 喔！代表 8,9,10,11,12 都適用的意思！
/n(斜線)|	那個 n 代表數字，亦即是『每隔 n 單位間隔』的意思，例如每五分鐘進行一次，則： */5 * * * * command 很簡單吧！用 * 與 /5 來搭配，也可以寫成 0-59/5 ，相同意思！
none|***

```
// 9:30 到 16:30 之間每小時都執行一次
crontab -e
30 9-16 * * * /home/ubuntu/miniconda3/bin/python /home/ubuntu/price_rank_scraper.py
```

## 3. Anaconda
```
// list install package
conda list

// install package
conda install pandas

// create  虛擬環境
conda create --name py3test python=3
// create new environment(include flask and panda)
conda create --name flask python=3 flask pandas
// active 
conda activate py3test
// deactive

//To activate this environment
conda activate py3test
//deactivate an active environment, use
conda deactivate
// show all environment
conda env list
// remove environment
conda remove --name myenv numpy
```

## 4. Miniconda(輕量化版本的 Anaconda)
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
// which python 檢視可以發現系統已經改以 Miniconda 的 Python 作為預設。
conda install requests beautifulsoup4 pandas
```

## 5. Django(創建 Web 應用程式和 Web API 的框架)

## 6. VsCode
```
// pylint(檢查 Python 程式碼)
python.exe -m pip install -U pylint --user

  WARNING: The script isort.exe is installed in 'C:\Users\RobertKao\AppData\Roaming\Python\Python37\Scripts' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
  Running setup.py install for wrapt ... done
  WARNING: The scripts epylint.exe, pylint.exe, pyreverse.exe and symilar.exe are installed in 'C:\Users\RobertKao\AppData\Roaming\Python\Python37\Scripts' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
Successfully installed astroid-2.2.5 isort-4.3.21 lazy-object-proxy-1.4.1 mccabe-0.6.1 pylint-2.3.1 typed-ast-1.4.0 wrapt-1.11.2
WARNING: You are using pip version 19.1.1, however version 19.2.1 is available.
You should consider upgrading via the 'python -m pip install --upgrade pip' command.

// select env
ctrl-shift-p --> Python: Select Interpreter

```

# format

## HTML
```python
from bs4 import BeautifulSoup
html_str = """
<html>
  <head>
    <title>The Avengers</title>
  </head>
  <body>
    <div id="header">
      <h1>Movies</h1>
    </div>
    <div id="movie-titles">
      <ul>
        <li id="movie-0" class="movies">
          <a href="https://www.imdb.com/title/tt0848228">The Avengers (2012)</a>
        </li>
        <li id="movie-1" class="movies">
          <a href="https://www.imdb.com/title/tt2395427">Avengers: Age of Ultron (2015)</a>
        </li>
        <li id="movie-2" class="movies">
          <a href="https://www.imdb.com/title/tt4154756">Avengers: Infinity War (2018)</a>
        </li>
        <li id="movie-3" class="movies">
          <a href="https://www.imdb.com/title/tt4154796">Avengers: Endgame (2019)</a>
        </li>
      </ul>
    </div>
  </body>
</html>
"""

soup = BeautifulSoup(html_str)
print(soup.find(id="movie-3").find("a").get("href"))
movie = soup.select("li#movie-3 a")
print(type(movie)) # list
print(movie[0]["href"])
```

## XPath-XML Path Language
單個正斜線 /：用來在樹狀結構中向下移動一層  
標記名稱：置放於正斜線之間用來定位資料  
中括號 []：用來指向同一個標記中的特定資料  
兩個正斜線 //：用來指向某個標記下的所有指定標記  
星號 * ：代表任意標記  
@ ：用來指定屬性，例如 id 、 class 或 href 等  
text() ：用來指定標記中所涵蓋的資料，即 <tag>...</tag> 中的 ...
```python
from lxml import etree

html_str = """
<html>
  <head>
    <title>The Avengers</title>
  </head>
  <body>
    <h1>Movies</h1>
    <p>The Avengers (2012)</p>
    <p>Avengers: Age of Ultron (2015)</p>
    <p>Avengers: Infinity War (2018)</p>
    <p>Avengers: Endgame (2019)</p>

    <div id="header">
      <h1>Movies</h1>
    </div>
    <div id="movie-titles">
    <a href="https://www.imdb.com/title/tt2395427">Avengers: Age of Ultron (2015)</a>
    <a href="https://www.imdb.com/title/tt4154756">Avengers: Infinity War (2018)</a>
    <a href="https://www.imdb.com/title/tt4154796">Avengers: Endgame (2019)</a>
    </div>
  </body>
</html>
"""
tree = etree.HTML(html_str)
print(tree)
print(tree.xpath("/html/body/p[4]/text()")[0])
print(type(tree)) # <class 'lxml.etree._Element'>
print(tree.xpath("/html/body/div[2]/a/@href")[1])
print(tree.xpath('//a/@href')[2])
```

## CSS Selector
#movie-3 > a {  
  font-size: 28px;  
}  
CSS Selector 指的便是大括號 {} 前所宣告的定位，簡單的 CSS Selector 可能由下列幾個元件所組成，與 XPath 有異曲同工之妙  
單個大於符號 >：用來在樹狀結構中向下移動一層（功能與 XPath 中的 / 相同）  
標記名稱：置放於大於符號之間用來定位資料  
:nth-of-type()：用來指向同一個標記中的特定資料（功能與 XPath 中的 [] 相同）  
空格：用來指向某個標記下的所有指定標記（功能與 XPath 中的 // 相同）  
星號 ＊：代表任意標記  
浮點 .：用來指定 class 屬性（功能與 XPath 中的 @ 功能相同）  
井字號 #：用來指定 id 屬性（功能與 XPath 中的 @ 功能相同）  
::text ：用來指定標記中所涵蓋的資料，即 <tag>...</tag> 中的 ...（功能與 XPath 中的 text() 相同）  
```python
from bs4 import BeautifulSoup

html_str = """
<html>
  <head>
    <title>The Avengers</title>
  </head>
  <body>
    <h1>Movies</h1>
    <p>The Avengers (2012)</p>
    <p>Avengers: Age of Ultron (2015)</p>
    <p>Avengers: Infinity War (2018)</p>
    <p>Avengers: Endgame (2019)</p>
  </body>
</html>
"""

soup = BeautifulSoup(html_str)
print(soup.select('html > body > p:nth-of-type(4)')[0].text)
print(soup.select('p:nth-of-type(4)')[0].text)
"""
```

# run

## 1. run jupyter notebook

```
// run jupyter notebook (http://localhost:8888)
jupyter notebook

// force port number
jupyter notebook --port <port_number>

// only start server not run browser
jupyter notebook --no-browser

// run
Ctrl + Enter

// 支援 linlie 繪圖
%matplotlib inline 

// jupyter run python(在選擇目錄的時候可以按一下tab鍵，會出現提示)
%run -i 目錄/my_python_file.py
```

## 2. socket

* **import pckage**

```python
import socket
```  


* **function**

```python
socket.socket([family], [type] , [proto] )
```

# python 語法
## common
```python
// del - 將完成賦值的物件自環境中刪除
hello_msg = "Hello Python!"
print(hello_msg)
del hello_msg

// help() 函數查詢函數的說明文件
help(print)

# 計算指令運算時間
big_array = np.random.random(10000000) #在0到1間亂數值取10000000個
%timeit min(big_array)
```

## function

* **os套件**

名稱			|說明
--------		|-----
system()		|	執行系統command
mkdir(E)		|	建立E目錄，如果E目錄已存在會發生錯誤
rmdir(E)		|	移除E目錄
remove(E)		|	移除E檔案，如果E是目錄就會出錯
getcwd()		|	取得目前所在路徑
rename(src, dst)|	將 src 改名為 dst

```python
import os
print(os.getcwd())
```

* **os.path有以下常用的函式**

名稱			|說明
--------		|-----
isfile(E) 		| E檔案是否存在
isdir(E) 		| E目錄是否存在
join(src, dst) 	| 拼接目錄，只有拼接，不會建立目錄
exists(E)		| 判斷文件或目錄是否存在
getsize(E) 		| 取得文件大小
abspath(E) 		| 獲得檔案的絕對路徑

```python
file = "day06-01.txt"
print("完整路徑名稱--->",os.path.abspath(file))  # 完整路徑名稱
print(file," 是否存在--->",os.path.exists(file)) # 是否存在
print(file," 檔案大小--->",os.path.getsize(file)) #取得檔案大小
```

* os.walk **取得目錄下所有檔案和目錄**

```python
import os
for root, dirs, files in os.walk("day06-dir"):
    for name in files:
        print("檔案--->",os.path.join(root, name))
    for name in dirs:
        print("目錄--->",os.path.join(root, name))
    print()
```

* **file**  
open(filename, mode)

文字	|說明
----	|----
r		|讀取
w		|寫入。檔案不存在則新增，檔案存在則寫入存在檔案
X		|寫入。只有當檔案不存在時才可寫入
a		|在檔案結尾處寫入
t		|文字
b		|二進位


```python
content = '''Python first   
測試中文
第三行
'''  # '''...'''  保留原本的格式
f = open('firstFile.txt','wt') # 寫入模式，檔案如果已經存在會被覆蓋
f.write(content)
f.close()
```

```python
#function 
def my_first_func():
    print('Call this function!')
my_first_func()
# 不定數目參數涵式
def sumNumber(*params):
    total = 0
    for param in params:
        total +=param
    return total
# 將function當作參數傳遞
def run_otherFunc(func):
    func(7,8)
run_otherFunc(GetArea)

# 常用內建函數
example1 = abs(-10)
print(example1)  #取得絕對值 輸出 10
example2 = chr(66)
print(example2)  #取得整數66的字元 輸出 B
example3 = divmod(33,6)
print(example3)  #取得33除以6的商數和餘數 輸出 (5, 3)
example4 = float(33)
print(example4)  #轉成浮點數 輸出 33.0
example5 = hex(33)
print(example5)  #轉成16進位 輸出 0x21
example6 = int(22.79)
print(example6)  #轉成整數(無條件捨去) 輸出 22
example7 = oct(33)
print(example7) #轉成八進位 輸出 0o41
example8 = ord("B")
print(example8) #取得Unicode編碼 輸出 66
example9 = pow(2,5)
print(example9) #取得2的5次方 輸出 32
example10 = round(22.79)
print(example10)  #轉成整數(四捨五入) 輸出 23
example11 = sum([11,22,33,44])
print(example11)  #取得list的總和 輸出 110


# 資料型態轉換
int() 轉換為整數
float() 轉換為浮點數
str() 轉換為字串

# 算術運算子
+, -, *, /, %, //(取得整除的商數), ** (次方, 7**2 = 49)

# 邏輯運算子
not, and, or  
&,|,^,~  

# type
print(type("xy"))
print(type(12))

# enumerate() 函數同時取得索引與數值
import numpy as np
arr = np.array([11, 12, 13, 14, 15])
for idx, val in enumerate(arr):
  print("位於索引值 {} 的數字是 {}".format(idx, val))

# print format
for i in range(nba_salary.shape[0]):
	print('{0:14}-{1:9}'.format(nba_salary.values[i][1], nba_salary.values[i][2]))
print("位於索引值 {} 的數字是 {}".format(idx, val))
# sep間隔 ,end結尾
print(100,200,300,sep="&",end="--")
# print format 
print("a=%d b=%d" % (10,20))
print("%s have %8.2f %s" % ("I", 99.0, "dollars"))

# input
name = input("Name:")

# string function
"HELLOW WORLD".lower() # 小寫
"hellow world".upper() # 大寫
"hellow world".title() # 第一個字母大寫
len("hellow world") # length
"Hello world".replace("l","!") # replace some char
# slipt string
"Hello my name is jiayi".split(" ")

# shuffle 隨機化代替列表中的項目
# random.shuffle(list)
row_indice = list(labeled_df.index)
random.Random(random_state).shuffle(row_indice)
shuffled = labeled_df.loc[row_indice, :]

#iolc 列切片及行切片
# 在 Python pandas 中可以使用 df.loc[m, n] 或 df.iloc[m, n] 兩個方法指定觀測值所在位置
# loc 基於行標籤和列標籤（x_label、y_label）進行索引
# iloc 基於行索引和列索引（index，columns） 都是從 0 開始

# reshape()  調整行列資料
X = np.arange(30).reshape((10, 3))

# dataframe.corr() 算出成對相關性(pairwise correlation)
```

## variable
```python
// type of variable
my_int = 87
my_float = 8.7
my_str = "Hello Python"
bool_true = True
bool_false = False
none_type = None
print(type(my_int))
print(type(my_float))
print(type(my_str))
print(type(bool_true))
print(type(bool_false))
print(type(none_type))

//
整數（int）
浮點數（float）
文字（str）
布林（bool）
None（NoneType）
// 
+ 、 - 、 * 、 / ：加減乘除
** ：次方
% ：回傳餘數
// ：回傳商數
//
我們使用成雙的單引號 '' 或成對的雙引號 "" 來建立文字類型（str），多數的時候使用單引號或者雙引號不會有任何分別。
// 運用文字時常會使用到的技巧是以特定格式印出（print with format），以 .format() 方法作為實踐的管道，以 {} 作文字或者以 {:f} 做數值等不同類型的嵌入
shaq_height = 216
shaq_weight = 147
shaq_bmi = shaq_weight/(shaq_height/100)**2
print("俠客歐尼爾的 BMI 為 {}%".format(shaq_bmi))
print("俠客歐尼爾的 BMI 為 {:.2f}%".format(shaq_bmi))
// Python 在文字上運算的彈性較大一些，可以利用 + 進行文字的合併（concatenation），以及利用 * 進行複製。
first_name = "Shaquille"
last_name = "O'Neal"
print(first_name + " " + last_name)
print((first_name + " " + last_name + " ") * 3)
// 布林
bool 只有 True 與 False 這兩個值
// 比較
// == 、 != ：等於以及不等於
// > 、 >= 、 < 、 <= ：大於、大於等於、小於以及小於等於
// is 、 is not ：是否為相同的值與類型
// and 、 or ：交集與聯集
// not ：非
// in ：是否存在於
print(8 is 7) # 判斷 8 與 7 是否為同樣的類別或值
print(8 is not 7) # 判斷 8 與 7 是否為相異的類別或值
print(not(8 > 7)) # 反轉 8 是否大於 7 的判斷
print("H" in "Hello world") # 判斷 H 是否存在於 Hello world 之中
// 在 Python 中， True 跟數值 1 相等； False 跟數值 0 相等
print(True == 1)
print(False == 0)
print(1 + True)
print(1 + False)
// None 是所謂的無值，或者可以用 NA 值（Not Available）或 NaN 值（Not a Number）去體會它，None 是無回傳值函數中的預設輸出值、也是搜索特徵函數找不到情況下的預設輸出值
def hello_world():
  pass
print(hello_world()) # None
print(type(hello_world())) # <class 'NoneType'>
// 使用 isinstance(x, classinfo) 函數判斷純量類型，其中 x 輸入物件名稱、 classinfo 輸入類型名稱
# 判斷是否為整數
print(isinstance(87, int))
print(isinstance("87", int))
# 判斷是否為浮點數
print(isinstance(87.0, float))
print(isinstance(87, float))
# 判斷是否為文字
print(isinstance("True", str))
print(isinstance(True, str))
# 判斷是否為布林
print(isinstance(False, bool))
print(isinstance("False", bool))
# 判斷是否為 None
print(isinstance(None, type(None)))
print(isinstance("None", type(None)))
// 轉換純量類型的函數
// int()：轉換純量為整數類型
// float()：轉換純量為浮點數類型
// bool()：轉換純量為布林類型
// str()：轉換純量為文字類型
print(int(8.7))
print(int(True))
print(int(False))
print(int("87"))
print(float(87))
print(float(True))
print(float(False))
print(float("87"))
print(str(87))
print(str(87.0))
print(str(True))
print(str(False))
// input 
player_name = input("請輸入球員姓名：")
player_height = input("請輸入球員身高（cm）：")
player_weight = input("請輸入球員體重（kg）：")
player_height = float(player_height)
player_weight = float(player_weight)
player_bmi = player_weight/(player_height*0.01)**2
print("{}的身體質量指數為：{:.2f}".format(player_name, player_bmi))

// list、tuple、set、dict 
# list
h = list(range(0,10)) # range to list
h2 = h*2              # douple list
print(h2)
print(h2[2:7])
del h2[1:3]  # del
print(h2)
print(len(h2)) # 串列元素數目
print(min(h2)) # 串列元素最小值
print(max(h2)) # 串列元素最大值
print(h2.index(4)) # 元素在串列中第一次出現的index
print(h2.count(5)) # 元素在串列中出現的次數
# A.append(E)：在A串列中加入E元素
# A.extend(B)：在A串列中加入B串列的元素
# A.insert(B)：在A串列中加入B串列
# A.pop()：取出串列中最後一個元素，並且移除元素
# A.remove(E)：移除A串列中第一個出現E元素
# A.reverse()：反轉串列的順序
# A.sort()：將串列做排序

# Tuple(元組)：不能修改的List 用括號
# list和tuple互相轉換
ironman_tuple = ("中信兄弟", "統一獅", "lamigo", "富邦悍將")
ironman_list = ["brother","lion","monkey","Guardians"]
tuple_to_list = list(ironman_tuple)
list_to_tuple = tuple(ironman_list)

# Dict(字典)：key-map的形式
ironman_dict = {"team":"中信兄弟","year":"2017","ranking":2}
print(ironman_dict["team"])
# del A[key]：刪除元素 A[key]
# A.clear()：刪除A Dict所有元素
# del A：刪除A Dict
```

## collection
```python
// list 列表 - []
play_list = ["Robert Kao", "Leo lin", "Jerry Hsu"]
int_list = list(range(0,10))
print(int_list)
print(len(play_list))
print(play_list[1]) # left 2nd
print(play_list[-1]) # rigit 1st
# 切割
print(int_list[1:3]) # [start:stop:step]
print(int_list[3:1:-1]) # step 參數如果指定為 -1 可以將 list 的資料順序顛倒
# function
int_list.append(x) 將 x 加入到 list 的末端
int_list.insert(index, x) 將 x 加入到 list 中指定的索引值位置
int_list.pop() 將 list 最末端的資料拋出
del int_list(index) 將指定位置的資料刪除
int_list.sort() 將 list 的資料預設以遞增排序
int_list.sort(reverse=True) 以遞減排序
list_data.index('string') 找值的位置
mylist3.remove('cat') remove

// tuple 多數的特性都與 list 相同，在建立的時候使用小括號 () 將希望儲存的資訊包括起來
# tuple 在索引與切割與 list 部分完全相同
# tuple 與 list 最大的差異在於 tuple 是不可變動（immutable）的資料結構，不具備任何包含新增、刪除與排序資料的操作
int_tuple = tuple(range(11,20))
print(int_tuple)

//dict 除了儲存資料（values）以外，還另外利用標籤（keys）來對資料作索引
# 在建立的時候使用大括號 {} 將希望儲存的資訊包括起來
play_dict = {
    "Fw" : "Robert Kao",
    "Lab": "Leo lin",
    "Direct" : "Jerry Hsu"
}
print(play_dict["Lab"])
print(play_dict.keys())
print(play_dict.values())
print(play_dict.items())
# dict 新增可以直接宣告 dict["key"] = value
# 使用 .keys() 、 .values() 與 .items() 可以分別取出 dict 中的所有標籤（Keys）、所有資料（Values）以及標籤加上資料（Items）

//set 是 Python 較為少用的資料結構，在建立的時候使用大括號 {} 將希望儲存的資訊包括起來，set 只會儲存獨一的資料，若輸入了重複的資訊，則會只記錄一筆
# set 還有一點與其他資料結構很大的差異是，無法使用中括號 [] 做索引或切割
positions = {"G", "G", "F", "F", "C"}
print(type(positions))
print(positions)

// example
play_list = ["Robert Kao", "Leo lin", "Jerry Hsu"]
play_tuple = tuple(play_list)
play_dict = {
    "Fw" : "Robert Kao",
    "Lab": "Leo lin",
    "Direct" : "Jerry Hsu"
}
play_set = set(play_list)

print(type(play_list))
print(type(play_tuple))
print(type(play_dict))
print(type(play_set))
```


## flow control
```python
// if
// and or not (True False)
height = 175
if (height<170):
    print("too low")
elif (height>200):
    print("too high")
else:
    print("height enough")

// for 
// continue 
man_list = ["Robert Kao", "Bill Lin", "Jerry Hsu"]
for man in man_list:
    print(man)
for i in range(3):
    print(man_list[i].split()[1].upper())

// while
man_list = ["Robert Kao", "Bill Lin", "Jerry Hsu"]
i = 0
while (i<3):
    print(man_list[i].split()[1].upper())
    i+=1
```

## 文字檔結構
* **CSV：純文字的方式儲存檔案資料，已逗號分隔資料，可用Microsoft Excel打開檔案。**  

```python
import csv
with open('day06-csv.csv', 'w', newline='') as csvfile:
    writer = csv.writer(csvfile) # 建立 CSV 檔寫入器
    writer.writerow(['股票', '收盤價', '單量'])
    writer.writerow(['台積電', 238, 23])
    writer.writerow(['大同', 40, 121])
    writer.writerow(['華新科', 174, 105])
    
# ---------------------------------------------------------- read

with open('day06-csv.csv', newline='') as csvfile:

  rows = csv.reader(csvfile)  # 讀取 CSV 檔案內容
  for row in rows:  # 以迴圈輸出每一列
    print(row)
```

* **XML：可延伸標記式語言，是一種標記式語言。**

```python
import xml.etree.ElementTree as ET
data = ET.Element('stock') #建立節點stock
tsmc = ET.SubElement(data, 'tsmc')  # 在stock節點底下建立子節點
close = ET.SubElement(tsmc, 'close')  
buy = ET.SubElement(tsmc, 'buy')  
close.set('name','收盤價') # 設定節點的名稱
buy.set('name','單量')  
close.text = '238'  
buy.text = '23'

mydata = ET.tostring(data)  
myfile = open("day06-xml.xml", "wb")  
myfile.write(mydata)  
myfile.close()
    
# ---------------------------------------------------------- read

tree = ET.parse('day06-xml.xml')  
root = tree.getroot()

for elem in root:  
    for subelem in elem:
        print(subelem.get('name'),"----->",subelem.attrib)
```

* **JSON：輕量級的資料交換語言**

```python
# JSON example
{
  "stock": [
    {
      "name": "台積電",
      "close": "238",
      "buy": "23"
    },
    {
      "name": "大同",
      "close": "40",
      "buy": "121"
    },
    {
      "name": "華新科",
      "close": "174",
      "buy": "105"
    }
  ]
}
# --------------------
import json

data = {}  
data['stock'] = []  
data['stock'].append({  
    'name': '台積電',
    'close': '238',
    'buy': '23'
})
data['stock'].append({  
    'name': '大同',
    'close': '40',
    'buy': '121'
})
data['stock'].append({  
    'name': '華新科',
    'close': '174',
    'buy': '105'
})

with open('day06-json.json', 'w') as outfile:  
    json.dump(data, outfile,ensure_ascii=False,indent=2)
    
# ---------------------------------------------------------- read

with open('day06-json.json') as json_file:  
    data = json.load(json_file)
    for p in data['stock']:
        print('股票: ' + p['name'])
        print('收盤價: ' + p['close'])
        print('單量: ' + p['buy'])
        print('')
```

* **YAML：是一個可讀性高，用來表達資料序列的格式**

```python
# YAML example 
stock:
  buy: '121'
  close: '238'
  name: '台積電'
# ------
import yaml
cfg = {
  "stock": dict(
      name='台積電',
      close='238',
      buy='121'
   )  
}
with open("day06_yml.yml", 'w') as outfile:
    yaml.dump(cfg, outfile, default_flow_style=False,allow_unicode=True) 
    
# ---------------------------------------------------------- read

with open("day06_yml.yml", 'r') as yml:
    contents = yaml.safe_load(yml)
    print("取得股票--->",contents['stock'])
```


# package

## datetime
```python
import datetime

# today/now 應該相同
import datetime
current_dt = datetime.datetime.now().strftime("%Y-%m-%d %X")
today = datetime.datetime.today().strftime('%Y%m%d')
# set date 
start = datetime.datetime(2018, 1, 1)
end = datetime.datetime(2018, 8, 1)
```

## beautifulsoup4 - 解析 HTML 資料
* **BeautifulSoup4(selector 分析網頁)**

function     | 說明
-------------|------
prettify()     |美化排版, soup.prettify()
tag_name       |tag data/nest tag data, soup.head, soup.head.title
tag_name.string|tag string, soup.head.title.string
find_all()     |all tag list,  soup.find_all('p')
link.get()     |get 屬性(attribute),link.get('href'), link.get('class')
get_text()     |get text, soup.get_text())

```python
# basic
html_doc = """
<html><head><title>The Dormouse's story</title></head>
<body>
<p class="title"><b>The Dormouse's story</b></p>
<p class="story">Once upon a time there were three little sisters; and their names were
<a href="http://example.com/elsie" class="sister" id="link1">Elsie</a>,
<a href="http://example.com/lacie" class="sister" id="link2">Lacie</a> and
<a href="http://example.com/tillie" class="sister" id="link3">Tillie</a>;
and they lived at the bottom of a well.</p>
<p class="story">...</p>
"""
# ------------
from bs4 import BeautifulSoup
soup = BeautifulSoup(html_doc, "html.parser")
# print(soup)
# prettify() : 美化排版
print(soup.prettify())
# direct get tag data
# .string --> text string
print("tag title :", prettify() : 美化排版)
print("tag head :", soup.head)
print("tag head.title :", soup.head.title)
print("tag head.title.string :", soup.head.title.string)
# find_all() : get all tag
print("tags p :", soup.find_all('p'))
# get() : get 屬性（attribute）
for link in soup.find_all('a'):
    print(link.get('href'), link.get('class'))
# find(id='link3') : find id
print("id link3 :", soup.find(id='link3'))
# get_text() : get text
print("all text :", soup.get_text())
```

```python
import requests
from bs4 import BeautifulSoup

r = requests.get("https://www.imdb.com/title/tt4154796/")
print(r)
# HTML git by text
r_data = r.text
# print(type(r_data))
# print(r_data)
soup = BeautifulSoup(r_data, "html.parser") # parser by html format

sel = soup.select("strong span")
#print(sel)
# get value in float type
for i in sel:
    print(float(i.text))

# get .poster img src value
sel = soup.select(".poster img")
print(sel)
for i in sel:
    print(i.get("src"))
```

* **beautifulsoup4 - example**  

```python
from bs4 import BeautifulSoup
html_str = """
<html>
  <head>
    <title>The Avengers</title>
  </head>
  <body>
    <div id="header">
      <h1>Movies</h1>
    </div>
    <div id="movie-titles">
      <ul>
        <li id="movie-0" class="movies">
          <a href="https://www.imdb.com/title/tt0848228">The Avengers (2012)</a>
        </li>
        <li id="movie-1" class="movies">
          <a href="https://www.imdb.com/title/tt2395427">Avengers: Age of Ultron (2015)</a>
        </li>
        <li id="movie-2" class="movies">
          <a href="https://www.imdb.com/title/tt4154756">Avengers: Infinity War (2018)</a>
        </li>
        <li id="movie-3" class="movies">
          <a href="https://www.imdb.com/title/tt4154796">Avengers: Endgame (2019)</a>
        </li>
      </ul>
    </div>
  </body>
</html>
"""

soup = BeautifulSoup(html_str)
print(soup.find(id="movie-3").find("a").get("href"))
movie = soup.select("li#movie-3 a")
print(type(movie)) # list
print(movie[0]["href"])
```

## requests(抓網頁)
Requests是一個Python HTTP庫

* **requests : disable SSL Warnings - json**  

```python
import requests
import urllib3

# disable SSL Warnings
urllib3.disable_warnings()
r = requests.get("https://opendata.epa.gov.tw/ws/Data/AQI/?$format=json", verify=False)
data_json = r.json()
# print(r.json())
# print(r.status_code)
i=0
for u in data_json:
    i+=1
    print(str(i) + " ***** " + str(u))
```

* **requests : support SSL certificate verify - json**

```python
# support SSL certificate verify
from urllib3 import PoolManager
import json
http = PoolManager()
r = http.request('GET', "https://opendata.epa.gov.tw/ws/Data/AQI/?$format=json")
# print(r.data)    # response data
# print(r.status)  # response status
data_json = json.loads(r.data) # data to json 
#print(data_json)
i=0
for u in data_json:
    i+=1
    # print(str(i) + " ***** " + str(u))
    print(str(i),"*****" ,u["County"] , u["SiteName"], u["PM2.5"])
```

* **requests : html**

```python
import requests
from lxml import etree
from io import BytesIO # bytes to str

r = requests.get("https://opendata.epa.gov.tw/ws/Data/AQI/?$format=xml", verify=False)
tree = etree.parse(BytesIO(r.content))

county = [t.text for t in tree.xpath('//Data/County')]
side_name = [t.text for t in tree.xpath('//Data/SiteName')]
pm25 = [t.text for t in tree.xpath('//Data/PM2.5')]

# zip for 打包成 tuple（元组)
for c, s, p in zip(county, side_name, pm25):
    print(c, s, p)
```


## nbextensions
```python
// 代碼補全 for jupyter notebook(nbextensions) install
conda install -c conda-forge jupyter_contrib_nbextensions

点开 Nbextensions 的选项，并勾选 Hinterland
```

## pandas(資料分析)
Pandas 是 python 的一個數據分析 lib  
Pandas就是建立在Numpy的基礎延伸的套件呢  
資料類型DataFrame:就像是我們在使用的excel表格一樣，是一個二維的數據有index和column  
資料類型Series:是一個類似陣列的物件，裡面可包含陣列的資料  

function     | 說明
-------------|------
df.head()    |查看前五列觀測值，可以加入參數 n 觀看前 n 列觀測值
df.tail()    |查看末五列觀測值，可以加入參數 n 觀看末 n 列觀測值
df.info()    |查看資料框的複合資訊，包含型別、外觀與變數型別等
df.describe()|查看數值變數的描述性統計，包含最小值、最大值、平均數與中位數等
df.read_csv()   |read csv(accept url)
df.dropna() |remove include NaN data
df.fillna(0)    |NaN fill value
df.sort_values('name') | sort by one field value - 不能改變原變數,要設成另一個變數
isin()     |check include date : employees["Team"].isin(["Legal","Scales","Product"])
notnull()  |value not null : mask = employees["Team"].isnull()
isnull()   |value null : mask = employees["Team"].notnull()
between()  |value between : employees[employees["Start Date"].between("2009-11-10","2010-01-20")]
set_index()|change index : df.set_index("Name", inplace=True),df.set_index( keys =["Pos","Player"], inplace=True)
reset_index() |reset index : df.reset_index(inplace=True)
df.rename()   |change column/index : df.rename( columns/index={"Rk":"Rk1","Age":"Age2",},inplace=True)
drop()        |drop some columns/row-不能改變原變數,要設成另一個變數 : df2 = df.drop(labels=["GS", "MP"], axis="columns")
sort_index()  |sort by index,df.sort_index(inplace=True)
index.get_level_values()|get index name, df.index.get_level_values(0),df.index.get_level_values("Player")
index.set_names()       |change index name, df.index.set_names(["Pos","Name"], inplace=True)
df["Player"].str        |str process, (df["Player"].str.lower(), df["Player"] = df["Player"].str.replace("Ja","Js")
pd.Series()   |create Series
pd.DataFrame()|create data frame,pd.DataFrame(np.random.randn(100, 4), index=pd.date_range('12/31/2017', periods=100), columns=list('ABCD'))

variable       | 說明
---------------|------
pd.__version__ |version
df.index       |查看資料框的列索引值
df.shape       |查看資料框的外觀，以 tuple 的型別回傳，(m, n) 表示 m 列觀測值，n 欄變數
df.columns     |查看資料框的變數名稱
df.loc['b']    |index 取出資料,也可取出多個 row : print(df.loc["Michael Jordan"])/print(df.loc[["Michael Jordan", "Dennis Rodman"]])
df.iloc[[0:4]  |get by index position : print(df.iloc[[0,4]]) # index 0 and 4 / print(df.iloc[0:4])  # index 0 to 3

* **groupby() - DataFrameGroupBy**

function     | 說明
-------------|------
size()                  |get per grounp counter 
get_group("group_value")|get group data in Dataframe

```python
# Series
# Series，是一個類似陣列的物件，裡面可包含陣列的資料
import pandas as pd
# -----------------------------
my_obj = pd.Series([4,7,-5,3])
print(my_obj)
print(my_obj.values)
print(my_obj.index)
#    RangeIndex(start=0, stop=4, step=1)
# change index not number
my_obj2 = pd.Series([8,9,10,11], index=['a','b','c','d'])
print(my_obj2.index, my_obj2["b"])
#    Index(['a', 'b', 'c', 'd'], dtype='object')
# chack index in 
print('a' in my_obj2)
# change directory to series
dic_data = {'name':'apple','birthday':'1996-1-1','luckynumber':7 }
my_obj3 = pd.Series(dic_data)
my_obj3
#    dtype: object
# Bool list to series
registration = [True,False,True,True]
registration = pd.Series(registration)
registration
#    dtype: bool

# DtatFrame
# DataFrame就像是我們在使用的excel表格一樣，是一個二維的數據有index和column
import pandas as pd
data = {'name': ['Bob', 'Nancy','Amy','Elsa','Jack'],
        'year': [1996, 1997, 1997, 1996, 1997],
        'month': [8, 8, 7, 1, 12],
        'day':[11,23,8,3,11]}
myframe = pd.DataFrame(data)
print(myframe)
# print(myframe["name"][1])
# change columns index
myframe2 = pd.DataFrame(data,columns=['name','year', 'day', 'month'])
print(myframe2)
# add columns (NaN : Not a Number)
myframe3 = pd.DataFrame(data,columns=['name','year', 'month', 'day', 'luckynumber'])
print(myframe3)
# set value
luckynumber = ['3','2','1','7','8']
luckynumber = pd.Series(luckynumber)
myframe3['luckynumber'] = luckynumber
print(myframe3)
# show specific 
print(myframe3['name'])
print(myframe3[['name', 'year']])
print(myframe3['name'][0:4]) # no show index 4
# insert data 
myframe3.insert(3,column="sport",value="Basketball")
print(myframe3)
# sort by one field value - 不能改變原變數,要設成另一個變數
print(myframe3.sort_values('name'))
print(myframe3)

# pandas data draw
%matplotlib inline
import pandas as pd
import numpy as np
df = pd.DataFrame(np.random.randn(100,4), index=pd.date_range('12/31/2017', periods=100), columns=list('ABCD'))
print(df)
df.plot()

# show some position data
import pandas as pd
import numpy as np
seriesObj = pd.Series(range(10),index=['a', 'a', 'b', 'b', 'b','c','c','c','c','c'])
seriesObj['c'] 
df = pd.DataFrame(np.random.randn(4,2),index=['a', 'a', 'b', 'b'])
print(df.index)
print(df.loc['b'])

#filter 
mask1 = employees["Team"] != "Marketing"
mask2 = employees["Start Date"] < "1980-01-01"
employees[(mask1 & mask2)] 
mask = employees["Team"].isin(["Legal","Scales","Product"])

# index aligment
import pandas as pd
# ---------------
csv_url = "https://storage.googleapis.com/ds_data_import/stats_per_game_chicago_bulls_1995_1996.csv"
# change index with certain field(1ts)
# df = pd.read_csv(csv_url, index_col="Name")
# change index with certain field(2nd)
df = pd.read_csv(csv_url)
df.set_index("Name", inplace=True)
print(df)
# check index
print(df.index)
# change column/index
df.rename( columns={"Rk":"Rk1",
                  "Age":"Age2",
                 },inplace=True)
df.rename( index={"Scottie Pippen":"Scottie Pippen1",
                  "Luc Longley":"Luc Longley2",
                 },inplace=True)
# drop some columns/row - 不能改變原變數,要設成另一個變數
# axis=1跟axis="columns"是一樣的！axis=0則是和asxis = "row"一樣
# df2 = df.drop(labels=["GS", "MP"], axis="columns")
df2 = df.drop(labels=["GS", "MP"], axis=1)
print(df2)
# get some row
print(df.loc["Michael Jordan"])
print(df.loc[["Michael Jordan", "Dennis Rodman"]])
# get by index position
print(df.iloc[[0,4]]) # index 0 and 4
print(df.iloc[0:4])  # index 0 to 3
# reset index
df.reset_index(inplace=True)
print(df.index)

# groupby() - DataFrameGroupBy
%matplotlib inline 
import pandas as pd
# --------------
csv_url = "https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.csv"
df = pd.read_csv(csv_url)
# print(df.columns)
# type is DataFrameGroupBy
grouped = df.groupby("Pos")
# print(grouped)
# print(type(grouped))
# get per group size
print(grouped.size())
# get group "SF" in pn dtat
print(grouped.get_group("SF"))
# grouped.sum() : get number column sum value

# multi index and index function
%matplotlib inline 
import pandas as pd
# --------------
csv_url = "https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.csv"
df = pd.read_csv(csv_url)
print(df.columns)
print(df["Pos"])
print(df)
# set multiplex
df.set_index( keys =["Pos","Player"], inplace=True)
# sort by index
df.sort_index(inplace=True)
print(df)
print(df["Ht"])
# get 1st index value
print(df.index.get_level_values(0))
# get specific index value
print(df.index.get_level_values("Player"))
# change index name
df.index.set_names(["Pos","Name"], inplace=True)
print(df)
#print(df.index)

# process relative str
%matplotlib inline 
import pandas as pd
# --------------
csv_url = "https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.csv"
df = pd.read_csv(csv_url)
print(df.columns)
#print(df)
#print(df["Pos"])
# Category 是由固定的且有限數量的變量組成的 故較省空間
df["Pos"] = df["Pos"].astype("category")
#print(df["Pos"])
print(df["Player"])
print(df["Player"].str.title())
print(df["Player"].str.lower())
# replace value
df["Player"] = df["Player"].str.replace("Ja","Js")
print(df["Player"])
# check include string
print(df["Player"].str.lower().str.contains("ron"))
# check start string
print(df["Player"].str.lower().str.startswith("js"))
# check end string
print(df["Player"].str.lower().str.endswith("ey"))
# split daya
print(df["Player"].str.split(" "))
print(df["Player"].str.split(" ").get(0))

# support SSL certificate verify
from urllib3 import PoolManager
import json
import pandas as pd

http = PoolManager()
r = http.request('GET', "https://opendata.epa.gov.tw/ws/Data/AQI/?$format=json")
data_json = json.loads(r.data) # data to json 
counties = [i["County"] for i in data_json]
site_name =  [i["SiteName"] for i in data_json]
pm25 =  [i["PM2.5"] for i in data_json]
# print(counties)
# print(site_name)
# print(pm25)

aqi_dict = {
        "County" : counties,
        "SideName" : site_name,
        "pm2.5" : pm25
}
#print(aqi_dict)

# 打包
df = pd.DataFrame(aqi_dict)
print(df)
# save csv file
df.to_csv("aqi.csv", index=False)
# write json file , ensure_ascii=False(show 中文)
with open("aqi.json", "w") as f:
    json.dump(aqi_dict, f, ensure_ascii=False)

# 在 Python pandas 中可以使用 df.loc[m, n] 或 df.iloc[m, n] 兩個方法指定觀測值所在位置
# 兩者用法差在於 df.loc[] 完全憑藉列索引值與欄索引值的標籤；而 df.iloc[] 完全憑藉相對位置
import pandas as pd
# ------------
numbers = [9, 23, 33, 91, 13]
players = ["Ron Harper", "Michael Jordan", "Scottie Pippen", "Dennis Rodman", "Luc Longley"]
df = pd.DataFrame()
df["number"] = numbers
df["player"] = players
print(df)
# ------------
df.index = ["PG", "SG", "SF", "PF", "C"]
print(df.loc[["SG", "SF", "PF"], ["number", "player"]]) # 以索引為準
print(df.iloc[[1, 2, 3], [0, 1]])                       # 以位置為準
# 排序
df.sort_index()                # 依照索引遞增排序
df.sort_index(ascending=False) # 依照索引遞減排序
df.sort_values(by="year").head()                  # 依照 year 遞增排序
df.sort_values(by="year", ascending=False).head() # 依照 year 遞減排序
# 依照 year 遞增排序再依照 continent 遞減排序
df.sort_values(by=["year", "continent"], ascending=[True, False]).head() 

# Python pandas 選擇資料框中特定變數會面對 Series 這樣的資料結構，而 Series 
# 就有完整的摘要方法供我們呼叫，像總和、平均或中位數等
import pandas as pd
csv_url = "https://storage.googleapis.com/learn_pd_like_tidyverse/gapminder.csv"
df = pd.read_csv(csv_url)
df[df.year == 2007]["pop"].sum()

# 在 Python pandas 中我們會使用 .groupby() 方法指定用來分組資料框的文字變數，
# 然後針對變數呼叫摘要方法，分組摘要的結果會以 Series 的型別回傳。
import pandas as pd
csv_url = "https://storage.googleapis.com/learn_pd_like_tidyverse/gapminder.csv"
df = pd.read_csv(csv_url)
grouped = df[df.year == 2007].groupby("continent")
grouped["pop"].sum()

# function iloc
import pandas as pd
df = pd.read_csv("https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996_per_game.csv")
# iloc() 取矩陣範圍資料
df_numerics = df.iloc[:, 4:]

# set for index(field trading_date)
df = df.set_index("trading_date")

# DataFrame only inculde some columns
data = {'names':['a','b','c','d','e'],
        'jan':[133,122,101,104,320],
        'feb':[122,132,144,98,62],
        'march':[64,99,32,12,65] }
df2 = pd.DataFrame(data,columns=['names','jan','feb'])
```

* **pandas-read csv說明**

參數      |說明
----------|----
sep       |預設為 , 因為 CSV 檔案就是以逗號（comma）分隔的檔案格式
header    |預設會將 CSV 檔案最上方的一列作為變數名稱，如果 CSV 檔案中沒有變數名稱，需指派 header=None
names     |假如已經指派 header=None 則 names 參數就需要輸入一組變數名稱的 list
skiprows  |指定在讀取時要略過多少列檔案上方的觀測值
skipfooter|指定在讀取時要略過多少列檔案下方的觀測值
nrows     |指定要讀入幾列觀測值
na_values |除了內建的遺漏值種類，還有哪些額外的字元要被視為遺漏值

```python
# 如果我們在 pd.read_csv() 中指定了 skiprows=1、header=None、names=[‘number’, ‘player’, ‘pos’, ‘ht’, ‘wt’, ‘birth_date’, ‘college’] 表示略過本來 CSV 中作為變數名稱的一列、資料中沒有變數名稱並且自行為資料的七個變數命名
csv_url = "https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.csv"
csv_df = pd.read_csv(csv_url, header=None, skiprows=1, names=['number', 'player', 'pos', 'ht', 'wt', 'birth_date', 'college'])
csv_df
```

* **pandas-read txt說明(將來僅用read_csv代替)**

副檔名為 .txt 純文字檔案跟 CSV 檔案的差異就在於分隔符號（separator）  
在 Python 中我們使用 pandas 的 pd.read_table() 方法；值得注意的參數是 sep 預設為 \t 意即 tab 鍵，  
因此面對以分號做為變數分隔的 TXT 檔案就要指定為 sep=";"  
```python
# pd.read_table() 指定 sep=";"
import pandas as pd

txt_url = "https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.txt"
txt_df = pd.read_table(txt_url, sep=";")
txt_df
```

* **pandas-read excel說明( .xlsx or .xls )**  

在 Python 中我們使用 pandas 的 pd.read_excel() 方法  

參數      |說明
----------|----
sheet_name|預設為 0，也就是排序最前面的工作表，可以利用整數來指定載入的工作表，也可以使用工作表名稱來指定
header    |預設為 0，也就是以最上方的一列作為變數名稱，指定 header=None 假如資料中沒有包含變數名稱
names     |假如已經指派 header=None 則 names 參數就需要輸入一組變數名稱的 list
usecols   |選擇哪幾個變數要載入
skiprows  |指定在讀取時要掠過多少列檔案上方的觀測值
skipfooter|指定在讀取時要略過多少列檔案下方的觀測值

```python
# pd.read_excel() 使用預設參數
import pandas as pd

xlsx_url = "https://storage.googleapis.com/ds_data_import/fav_nba_teams.xlsx"
chicsgo_bulls = pd.read_excel(xlsx_url)
chicsgo_bulls

# 例如指定讀取第二個工作表、並選取部分儲存格範圍 A7 至 C16

# pd.read_excel() 指定工作表與讀取範圍
import pandas as pd

xlsx_url = "https://storage.googleapis.com/ds_data_import/fav_nba_teams.xlsx"
boston_celtics = pd.read_excel(xlsx_url, sheet_name='boston_celtics_2007_2008', skiprows=6, header=None, names=['number', 'player', 'pos'], usecols=[0, 1, 2])
boston_celtics
```

* **pandas-read json說明**  

JSON 檔案若是儲存在雲端，利用 requests 模組的 get() 函數搭配 .json() 方法就可以載入，成功之後會以 dict 型別供後續操作。
```python
# JSON 檔案儲存在雲端
from requests import get

json_url = 'https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.json'
chicago_bulls_dict = get(json_url).json()
print(type(chicago_bulls_dict))
chicago_bulls_dict
```

## pandas_datareader.data(get data from web)
pip install pandas_datareader  
import pandas_datareader.data as web  
直接到網路上跟合作的廠商抓資料(無須輸入任何API網址)  
[Remote Data Access list](https://pandas-datareader.readthedocs.io/en/latest/remote_data.html#remote-data-google)  

function     | 說明
-------------|------
DataReader() |read data from seb site, data = web.DataReader("F", 'yahoo', start, end)


```python
# pandas_datareader read and plot
%matplotlib inline
import pandas_datareader.data as web
import datetime
# ------------------------------
start = datetime.datetime(2018, 1, 1)
end = datetime.datetime(2018, 8, 1)
data = web.DataReader("F", 'yahoo', start, end)
# show plot
# print(data)
# data.plot()
# show Colse data
data.plot(y="Close") # also data["Close"].plot() - but if run "data.plot()" no show
# show 2 items
print(data.columns)
data[["High", "Low"]].plot()
```


## lxml
lxml is the most feature-rich and easy-to-use library for processing XML and HTML in the Python language

## pyquery 解析 HTML 資料
conda install pyquery
```python
import requests
from pyquery import PyQuery

r = requests.get("https://www.imdb.com/title/tt4154796/")
print(r)
# HTML git by text
#r_data = r.text
d =  PyQuery(r_data)
#print(d)

# get value
sel = d("strong span").items()
print(sel) # only show point : <generator object PyQuery.items at 0x000002317540BDE0>
print(d("strong span")) # show <span itemprop="ratingValue">8.7</span>
for i in sel:
    print(float(i.text()))
    
# get src
sel = d(".poster img").items()
print(d(".poster img")) 
for i in sel:
    print(i.attr("src"))

#get data for some condition
from pyquery import PyQuery as pq
# -----------
stats_url = "https://www.basketball-reference.com/players/p/piercpa01.html"
html_doc = pq(stats_url)
pts_css = "#per_game .full_table .right:nth-child(30)"
ast_css = "#per_game .full_table .right:nth-child(25)"
reb_css = "#per_game .full_table .right:nth-child(24)"
pts = [float(p.text) for p in html_doc(pts_css)]
ast = [float(a.text) for a in html_doc(ast_css)]
reb = [float(r.text) for r in html_doc(reb_css)]
```

## selenium-操控瀏覽器來擷取 HTML
Seleninm: 它能控制你的瀏覽器,有模有樣地學人類”看”網頁  
conda install selenium  
function(input): clear(), send_key(), submit(), click()
```python
import time
from selenium import webdriver

driver = webdriver.Chrome('./chromedriver')  # Optional argument, if not specified will search path.
driver.get('http://www.google.com/xhtml');
time.sleep(5) # Let the user actually see something!
search_box = driver.find_element_by_name('q')
search_box.send_keys('ChromeDriver')
search_box.submit()
time.sleep(5) # Let the user actually see something!
driver.quit()

# ==== 2nd sample ====
from selenium import webdriver
# open
imdb_home = "https://www.imdb.com"
driver = webdriver.Chrome('./chromedriver')  # Optional argument, if not specified will search path.
driver.get(imdb_home)
print(driver.current_url)
driver.close()
```

## flask
```
// create new environment(include flask and panda)
conda create --name flask python=3 flask pandas
// 載入 flask 工作環境
conda activate flask
// create directory 
mkdir gapminder-api
// get gapminder.csv file 
https://s3-ap-northeast-1.amazonaws.com/sqlite-demo-data/gapminder.csv
// add file 
api.py
// run flask api
python apy.py
// open by browser
http://127.0.0.1:5000
```
* **flask-apy.py**

```python
import flask

app = flask.Flask(__name__)
app.config["DEBUG"] = True

@app.route('/', methods=['GET'])
def home():
        return "<h1>Hello Flask</h1>"
    
app.run()
```

## firebase_admin
Firebase Admin SDK for Python  
// install firebase_admin(conda not support  
pip install firebase_admin  

# Numpy
支援高階大量的維度陣列與矩陣運算，此外也針對陣列運算提供大量的數學函式函式庫  
Numpy是一個提供矩陣運算非常非常非常好用的工具  

function     | 說明
-------------|------
np.array()       |set to ndarry
np.arange(10)  |generate by range
pd.date_range()|set date for pd, index=pd.date_range('12/31/2017', periods=100)
np.ones(5)     |可以創建任意維度和元素個數的數組，其元素值均為1
np.zeros(3,int)|創建的數組元素類型是浮點型的，如果要使用其他類型，可以設置dtype參數進行聲明
		       |np.zeros(4,dtype={'names':('name','number','team'),'formats':('U10','i2','U10')})
np.empty([2,3])|只是它所常見的數組內所有元素均為空，沒有實際意義
np.full((4,2), 2.2) |建立一個arry, 建立一個內容為2.2 4x2 的浮點數陣列
np.linspace()       |建立一個內容介於兩數間的array, np.linspace(-np.pi, np.pi, 100) 
random.randn()  |隨意數+,-,<0,>0...
.random.randint()|整數隨意數, .random.randint(low[, high, size, dtype]) - low (inclusive) to high (exclusive)
.random.random()|隨意數[0,1):>=value<1-,.random.random(size=None),numpy.random.ranf(size=None) also same
.random.normal()|隨意數 for normal (Gaussian) distribution
np.sin(x\*4\*np.pi)|set to ndarry by sin function
np.abs() |絕對值
np.exp(),exp2(),power()|指數,e^x,2^x,10^x
np.log(),log2(),log10()|對數
.multiply.outer(y,y)|外積
np.mean()  	|平均值
np.sum()  	|總和
np.min()  	|最小值
np.max()  	|最大值
np.cumsum() |回傳累積的數值(array)
np.std()  	|標準差
np.prod		|所有元素的乘積
np.var		|變異量
np.argmin	|找出最小值的索引
np.argmax	|找出最大值的索引
np.median	|元素的中位數
np.any		|當陣列中有任一值是True或是非零值時傳回True
np.all		|當陣列中有所有值是True或是非零值時傳回True
np.save('my_array', x)  |save array
np.load('my_array.npy') |load array
myArr = np.loadtxt('my_txt.txt', delimiter=',') |load text file
np.savetxt('txtfile.txt', myArr)                |save text file
df.reshape(4,1)|array 改變維度
np.concatenate([x,y])|concatenate-串接陣列
np.vstack([x,y])     |vstack-垂直串接
np.hstack([x,y])     |hstack-水平串接
np.split(z,[3,5,8])	|split-分割
np.hsplit(z,[2])	|hsplit-垂直分割
np.vsplit(n,[2])	|vsplit-水平分割
np.count_nonzero(x) |no zero number
df.sort()|排序
np.argsort(x)|傳回被排序過的索引值
np.sort(y,axis=0)) |排序依維度 sort by 1st dim
np.random.randint(0,50,size=10)|部分排序:Partitioning

variable       | 說明
---------------|------
ndim			|維度
shape			|矩陣大小
dtype			|dtype
itemsize		|item bytes
nbytes 			|total bytes
T 				|翻轉維度
base            |相關

**numpy的資料型態有以下幾種***  

字元|說明
----|------
b	|位元組
i	|有號整數
u	|無號整數
f	|浮點數
c	|複數浮點數
S,a	|字串
U	|unicode字串
v	|void

```python
# numpy ndarray
import numpy as np
# direct set vale + set dtype
arr1 = np.array([[1.2, 2.2 ,0.65], [3.2, 34.2 ,5.65]], dtype=complex)
print(arr1)
print(type(arr1[1][2]))
print(arr1[1][2])
# set by list
list1 = [3,7,5]
arr2 = np.array(list1)
print(arr2)
# 維度
print(arr1.ndim, arr2.ndim)
# 矩陣大小
print(arr1.shape, arr2.shape)
# dtype
print(arr1.dtype, arr2.dtype)

# array 相乘,改變維度,一維 + 二維, 翻轉維度,base 
import numpy as np
x = np.arange(4)
y = np.arange(5,9)
# array 相乘
print(x, y, x*y, x*10)
# array 改變維度
x2 = x.reshape(4,1)
print(x, x2)
print(x.shape, x2.shape)
# 一維 + 二維
y2 = np.ones(5)
print(type(y2[0]))
print(y2.shape)
print(y2+x2)
# 翻轉維度
x1 = np.ones([10,2])
y1 = x1.T
print(x1,y1)
# base
x = np.arange(4)
xx = x.reshape(4,1)
print(xx.base in x)

# array 隨意數,平均值,總和,最小值,最大值,累積的數值,標準差
import numpy as np
# 產生隨意數+,-,<0,>0...
print(np.random.randn())
# 產生整數隨意數
# (low, high=None, size=None, dtype='l')
print(np.random.randint(1,10,size=10))
x = np.random.randn(5,4)
print(x)
# print(x.mean(),x.sum(),x.min(),x.max(),x.cumsum(), x.std())
# ----------------
print(x.mean()) # 平均值
print(x.sum())  # 總和
print(x.min())  # 最小值
print(x.max())  # 最大值
print(x.cumsum()) # 回傳累積的數值(array)
# 標準差 std = sqrt(mean(abs(x - x.mean())**2))
# 標準差應用於投資上，可作為量度回報穩定性的指標。標準差數值越大，代表回報遠離過去平均數值，
# 回報較不穩定故風險越高。相反，標準差數值越小，代表回報較為穩定，風險亦較小。
print(x.std()) # 標準差

# numpy file control
import numpy as np
x = np.arange(10)
print(x)
# save array and load
np.save('my_array', x)
np.load('my_array.npy')
# save multi array to a file
y = np.arange(10,20)
print(y)
# save multi array and load
np.savez('my_archive.npz', a=x, b=y)
load_a = np.load('my_archive.npz')
print(load_a["a"])
print(load_a["b"])
# load/save text 
myArr = np.loadtxt('my_txt.txt', delimiter=',')
np.savetxt('txtfile.txt', myArr)

import numpy as np
# -----------------
# array
np1 = np.array([1, 2, 3])
np2 = np.array([3, 4, 5])
# 陣列相加
print(np1 + np2) # [4 6 8]
# 顯示相關資訊
print(np1.ndim, np1.shape, np1.dtype) # 1 (3,) int64 => 一維陣列, 三個元素, 資料型別
# 從檔案取資料
# npd = np.genfromtxt('data.csv', delimiter=',')
# start,endm array number
np.linspace(2.0, 3.0, num=5)
# pi
a = np.linspace(-np.pi, np.pi, 100) 
print(a)
# sin
b = np.sin(a)
print(b)
# random : 建立一個 3x3 隨機矩陣
from numpy.random import rand
c = rand(3, 3) 
print(c)

# numpy - random,串接(concatenate),分割(split)
import numpy as np
# .random.random(size=None) [0,1):>=value<1
# .random.random(size=None),numpy.random.ranf(size=None) also same
#- print(np.random.random(3))
#random int : .random.randint(low[, high, size, dtype]) - low (inclusive) to high (exclusive)
ran_int = np.random.randint(0,10,(3,3))
#- print(ran_int)
#- print(ran_int.shape, ran_int.ndim, ran_int.size, ran_int.dtype, ran_int.itemsize, ran_int.nbytes)
# .random.normal(loc=0.0, scale=1.0, size=None)
# random samples from a normal (Gaussian) distribution
# loc Mean (“centre”) of the distribution. - 此概率分佈的均值（對應著整個分佈的中心centre）
# scale Standard deviation (spread or “width”) of the distribution. - 此概率分佈的標準差（對應於分佈的寬度，scale越大越矮胖，scale越小，越瘦高）
# size Output shape
#- print(numpy.random.normal(0,1,(3,3)))
# 串接(concatenate-串接陣列,vstack-垂直串接,hstack-水平串接)
x = np.arange(1,4)
y = np.array([4,5,6])
#- print(np.concatenate([x,y]))
#- print(np.vstack([x,y]))
#- print(np.hstack([x,y]))
# 分割(split-分割,hsplit-垂直分割,vsplit-水平分割)
z = np.arange(1,10)
print(np.split(z,[3,5,8])) # 分割點
print(np.hsplit(z,[2]))
n = z.reshape(3,3)
print(np.vsplit(n,[2]))

# numpy - random,串接(concatenate),分割(split),broadcasting,比較運算子,get some value 
import numpy as np
# .random.random(size=None) [0,1):>=value<1
# .random.random(size=None),numpy.random.ranf(size=None) also same
#- print(np.random.random(3))
#random int : .random.randint(low[, high, size, dtype]) - low (inclusive) to high (exclusive)
ran_int = np.random.randint(0,10,(3,3))
#- print(ran_int)
#- print(ran_int.shape, ran_int.ndim, ran_int.size, ran_int.dtype, ran_int.itemsize, ran_int.nbytes)
# .random.normal(loc=0.0, scale=1.0, size=None)
# random samples from a normal (Gaussian) distribution
# loc Mean (“centre”) of the distribution. - 此概率分佈的均值（對應著整個分佈的中心centre）
# scale Standard deviation (spread or “width”) of the distribution. - 此概率分佈的標準差（對應於分佈的寬度，scale越大越矮胖，scale越小，越瘦高）
# size Output shape
#- print(numpy.random.normal(0,1,(3,3)))
# 串接(concatenate-串接陣列,vstack-垂直串接,hstack-水平串接)
x = np.arange(1,4)
y = np.array([4,5,6])
#- print(np.concatenate([x,y]))
#- print(np.vstack([x,y]))
#- print(np.hstack([x,y]))
# 分割(split-分割,hsplit-垂直分割,vsplit-水平分割)
z = np.arange(1,10)
print(np.split(z,[3,5,8])) # 分割點
print(np.hsplit(z,[2]))
n = z.reshape(3,3)
print(np.vsplit(n,[2]))
# broadcasting
a = np.array([0,1,2])
print(a + 5)
b = np.arange(3)[:, np.newaxis]
print(b)
# 比較運算子(==,!=,<,<=,>,>=)
x = np.array([1,2,3,4,5])
print(x>2)
np.count_nonzero(x>2) # false number
# get some value 
x = np.random.randint(10, size=(4,5))
print(x)
print(x[(x>5) & (x <8)])

# numpy - 排序的索引值,排序,排序依維度,部分排序,建立結構化的資料
import numpy as np
x = np.random.randint(0,100, size=5)
print(x)
# 傳回被排序過的索引值
print(np.argsort(x))
# 排序
x.sort()
print(x)
# 排序依維度
y = np.random.randint(0,100, (4,4))
print(y)
print(np.sort(y,axis=0)) # sort by 1st dim
print(np.sort(y,axis=1)) # sort by 2nd dim
# 部分排序:Partitioning - 最小四個元素放在左邊(順序隨意)
x = np.random.randint(0,50,size=10)
print('x--------------->',x)
print(np.partition(x,4))
# 建立結構化的資料
team =np.zeros(4, dtype={'names':('name','number','team'),'formats':('U10','i2','U10')})
# 建立標題name 資料型別是unicode字串 長度10
# 建立標題number 資料型別是有號整數 長度2
# 建立標題team 資料型別是unicode字串 長度10
print(team)
print(team.dtype)
team['name'] =['彭政閔','林智勝','蘇偉達','陽耀勳']
team['number'] = [23,32,96,23]
team['team'] = ['兄弟象','兄弟象','兄弟象','lamigo']
print(team)
print(team['number'])
```

## squarify
pip install squarify  
```python
# 樹狀圖(treemap)
%matplotlib inline 
import pandas as pd
import matplotlib.pyplot as plt
import squarify

csv_url = "https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.csv"
df = pd.read_csv(csv_url)
grouped = df.groupby("Pos")
pos = grouped["Pos"].count()
squarify.plot(sizes=pos.values, label=pos.index, color=["red", "green", "blue", "grey", "yellow"], alpha=0.4)
plt.axis('off')  #不show座標刻度
plt.title("1995-1996 Chicago Bulls roster") # 抬頭
plt.show()
```

## chart-studio --> plotly
pip install chart-studio  
api key = "bEtPpStSQgWRADCmGGe9"  
```python
import chart_studio.plotly as py
import plotly.graph_objs as go
// --------------------------
tsmc = get_ohlc('2330')
# -- show Candlestick fig --
trace = go.Candlestick(x=tsmc.index,
                       open=tsmc["open"],
                       high=tsmc["high"],
                       low=tsmc["low"],
                       close=tsmc["close"])
# no show bottom fig
layout = go.Layout(
    xaxis = dict(
        rangeslider = dict(
            visible = False
        )
    )
)
fig = go.Figure(data=trace, layout=layout)
fig.show()
# update to plotly wibside(need API key)
py.sign_in('kyp001', 'bEtPpStSQgWRADCmGGe9') # Use your own plotly Username / API Key
py.iplot(fig, filename='simple_candlestick')
```

## folium
pip install folium  
```python
```

## scipy
SciPy就是以Numpy為基礎做科學、工程的運算處理的package，包含統計、優化、整合、線性代數、傅立葉轉換圖像等較高階的科學運算  

## StatsModels
Statsmodels 是一個 Python 模塊，它為統計數據分析提供了許多機會，例如統計模型估計、執行統計測試等。在它的幫助下，你可以實現許多機器學習方法並探索不同的繪圖可能性。  

## sklearn(Scikit-learn)
* **sklearn.tree**

function     | 說明
-------------|------
DecisionTreeClassifier() |create DecisionTreeClassifier
fit()                    |傳入資料
predict()                |預測label
score(X_test,y_test)     |算出準確度

```python
# sklearn.tree 
from sklearn import tree
# 1:皺 0:光滑 
features = [[150,1],[170,1],[130,0],[140,0]]
# 0:橘子 1:蘋果
labels = [0, 0, 1, 1]
clf =tree.DecisionTreeClassifier()
clf = clf.fit(features, labels)
wantPredict = clf.predict([[200,0]])
# return same as label define
print(wantPredict) 
if wantPredict == [1]:
    print('This is an apple')
elif wantPredict == [0]:
    print('This is an orange')
```

* **sklearn.neighbors.KNeighborsClassifier-K-近鄰演算法(K Nearest Neighbor)**

```python
# K-近鄰演算法(K Nearest Neighbor)
from sklearn import datasets
from sklearn.model_selection import train_test_split
from sklearn.neighbors import KNeighborsClassifier
# load 鳶尾花的資料
iris = datasets.load_iris()
# set data abd label variable
iris_data = iris.data
iris_label = iris.target
# 劃分 訓練資料與測試資料
train_data , test_data , train_label , test_label = train_test_split(iris_data,iris_label,test_size=0.2)
# 算出預估結果
knn = KNeighborsClassifier()
knn = knn.fit(train_data,train_label)
print(knn.predict(test_data))
# 列出實際答案比較
print(test_label)
```

* **sklearn.linear_model.LinearRegression 線性迴歸(linear regression)**

```python
# sklearn.linear_model.LinearRegression 線性迴歸(linear regression)
%matplotlib inline
from sklearn.linear_model import LinearRegression
from sklearn import datasets
import matplotlib.pyplot as plt
# generate random data
# sample data=200, feature=1 , label=1, noise設為10，這樣資料會比較分散一點
x,y = datasets.make_regression(n_samples=200, n_features=1, n_targets=1, noise=10)
model = LinearRegression()
model = model.fit(x, y)
predict = model.predict(x[:200,:])
# draw 線性迴歸線
plt.plot(x,predict,c="red")
plt.scatter(x, y)
plt.show()
```

* **sklearn.preprocessing-特徵標準化(normalization) for 提高準確度**
* **sklearn.svm**

```python
# 特徵標準化(normalization) - 提高準確度
# sklearn.svm.SVC
%matplotlib inline
from sklearn import preprocessing
from sklearn.datasets.samples_generator import make_classification
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.svm import SVC
import warnings
# mask warn --> base.py:196: FutureWarning: The default value of gamma will change from 'auto' to 'scale' in version 0.22 
# to account better for unscaled features. Set gamma explicitly to 'auto' or 'scale' to avoid this warning.
#  "avoid this warning.", FutureWarning)
warnings.filterwarnings("ignore", category=FutureWarning, module="sklearn", lineno=196)
X,y = make_classification(n_samples=300, n_features=2, n_redundant=0, n_informative=2,
                         random_state=3, scale=100, n_clusters_per_class=1)
# 標準化
X = preprocessing.scale(X)
# split test data
X_train,X_test,y_train,y_test = train_test_split(X,y,test_size=0.2)
# SVC分類法
clf = SVC()
clf.fit(X_train,y_train)
result = clf.score(X_test,y_test)
print(result)
# show plot
plt.scatter(X[:,0], X[:,1] ,c=y)
plt.show()
```

* **sklearn.model_selection.cross_val_score-交叉驗證**

```python
# 交叉驗證(Cross validation) - 計算多次準確度 - 此為 K-Fold Cross Validation(k交叉驗證)
# 交叉驗證主要分為以下幾類
# k-folder cross-vailation
# kk folder cross-vaildation
# least-one-out cross-validation
# 10-fold corss validation
from sklearn.model_selection import cross_val_score
from sklearn import datasets
from sklearn.neighbors import KNeighborsClassifier
import matplotlib.pyplot as plt
# load 鳶尾花的資料
iris = datasets.load_iris()
# set data abd label variable
X = iris.data
y = iris.target
# change n_neighbors
k_range = range(1,31)
k_score = []
for k_number in k_range:
    knn = KNeighborsClassifier(n_neighbors=k_number)
    # 算出精準度  - 計算多次
    # cv:計算幾次 scoring='accuracy'精準度
    scores = cross_val_score(knn, X,y, cv=10 , scoring='accuracy')
    # print(scores)
    # print(scores.mean())
    k_score.append(scores.mean())
# draw 
plt.plot(k_range, k_score)
plt.xlabel("Neighbors")
plt.ylabel("Score")
plt.show()
```

* **sklearn.externals.joblib - 將訓練的model儲存起來**

```python
# sklearn.externals.joblib - 將訓練的model儲存起來
# load model and save
from sklearn.externals import joblib
from sklearn import datasets
from sklearn.svm import SVC
# load 鳶尾花的資料
iris = datasets.load_iris()
X = iris.data
y = iris.target
# SVC分類法
clf = SVC()
clf.fit(X,y)
#save file
joblib.dump(clf,'clf.pkl')
#load file
clf2 = joblib.load('clf.pkl')
# predict
print(clf2.predict(X[0:10]))
```

* **sklearn.datasets**  

測試資料集  
```python
# load 鳶尾花的資料
iris = datasets.load_iris()
# generate random data
# sample data=200, feature=1 , label=1, noise設為10，這樣資料會比較分散一點
x,y = datasets.make_regression(n_samples=200, n_features=1, n_targets=1, noise=10)
```

* **sklearn.model_selection.train_test_split**  

測試資料劃分
```python
# 劃分 訓練資料與測試資料
train_data , test_data , train_label , test_label = train_test_split(iris_data,iris_label,test_size=0.2)
```

## warnings
mask warning

```python
import warnings
# mask warning --> base.py:196: FutureWarning: The default value of gamma will change from 'auto' to 'scale' in version 0.22 
# to account better for unscaled features. Set gamma explicitly to 'auto' or 'scale' to avoid this warning.
#  "avoid this warning.", FutureWarning)
warnings.filterwarnings("ignore", category=FutureWarning, module="sklearn", lineno=196)
```

# 基礎視覺化
matplotlib 中的 pyplot 模組、seaborn 模組、pandas 模組**  

## matplotlib
Matplotlib是Python繪圖  
%matplotlib inline  

function     | 說明
-------------|------
plt.show()    |最後畫圖
plt.plot()    |線圖,可同時設多條線, (x,y,color=,marker="o"設定點,linestyle="--" 顯示虛線)
plt.pie()     |圓餅圖
plt.bar()     |長條圖  bar(x, height, width=0.8透明度, bottom=None, *, align='center', data=None, **kwargs)
setp(line1, marker="o", linestyle="--")|set some line configure
plt.title()   |title
plt.xlabel()  |xlabel
plt.ylabel()  |ylabel
plt.xticks()  |x 標示 plt.xticks(np.arange(0, 3)+0.3, ["Math", "Reading", "Scilent"])
plt.yticks()  |y 標示
plt.grid(True)|顯示格線
plt.text()    |標示文字 text(x, y, s, fontdict=None, withdash=<deprecated parameter>, **kwargs) s=show text
plt.legend()  |圖例 plt.legend(title = "Court") 
plt.xlim()    |x 顯示範圍 xlim((left, right), left, right = xlim() - return the current xlim
plt.ylim()    |y 顯示範圍 ylim(bottom, top), bottom, top = ylim()  - return the current ylim
plt.title(".")|抬頭
plt.axis('off')  |不show座標刻度
for item in data |item data : item.get_height(),item.get_x()

* **matplotlib-->pyplot**

```python
# matplotlib pyplot plot(線圖 line plot)
%matplotlib inline
import matplotlib.pyplot as plt
years = [1950,1960,1965,1970,1975,1980,
        1985,1990,1995,2000,2005,
        2010,2015]
pops = [2.5,2.7,3,3.3,3.6,4.0,
        4.4,4.8,5.3,6.1,6.5,6.9,7.3]
deaths = [1.2,1.7,1.8,2.2,2.5,2.7,2.9,3,3.1,3.2,3.5,3.6,4]
# x, y list , color=, "--":顯示虛線
# 可同時設多條線
line1 = plt.plot(years, pops, color=(255/255,100/255,100/255))
plt.plot(years, deaths, "--", color=(100/255,100/255,255/255))
# set some for line, marker="o"設定點  linestyle="--" 顯示虛線
plt.setp(line1, marker="o", linestyle="--")
plt.title("Population Growth") # title
plt.xlabel("Year")              # xlabel
plt.ylabel("Population in billions") # yabel
plt.grid(True) # 顯示格線
plt.show()

# matplotlib pyplot plot(線圖 line plot) - draw sin
%matplotlib inline
import numpy as np
import matplotlib.pyplot as plt
# set array for x
x = np.arange(0, 1, 0.01)
# get y array by sin function
y1 = np.sin(x*4*np.pi)
y2 = np.sin(x*2*np.pi)
# print(x)
# print(y1)
# plot and set configure
lines=plt.plot(x,y1,x,y2)
plt.setp(lines,linestyle="--")
plt.show()

# matplotlib pyplot plot(圓餅圖 pie)
%matplotlib inline
import numpy as np
import matplotlib.pyplot as plt
# ------------------------
labels = 'A','B','C','D','E','F'
size = [33,52,12,17,62,48]
separated = (.1,0,0,0,.2,0)
# (size, labels=標示, autopct=顯示百分比, explode=餅分開距離)
plt.pie(size, labels=labels, autopct="%1.1f%%",explode=separated)
# axis('equal')避免比例壓縮為橢圓
plt.axis('equal')
plt.show()

# matplotlib pyplot plot(圓餅圖 pie 2nd) 
%matplotlib inline
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd

data = {'names':['a','b','c','d','e'],
        'jan':[133,122,101,104,320],
        'feb':[122,132,144,98,62],
        'march':[64,99,32,12,65] }
df1 = pd.DataFrame(data)
df1['total'] = df1['jan']+df1['feb']+df1['march']
colors = [(1,.4,.4),(1,.6,1),(.5,.3,1),(.7,.7,.2),(.6,.2,.6)]
# print(df1)
# (size, labels=標示, colors=顏色, autopct=顯示百分比, explode=餅分開距離)
plt.pie(
    df1['total'],
    labels = df1['names'],
    colors = colors,
    autopct='%1.1f%%'
)
plt.axis('equal')
plt.show()

# matplotlib pyplot plot(長條圖 bar) 
%matplotlib inline
import numpy as np
import matplotlib.pyplot as plt
# ------------------
def createLabel(data):
    # data include artist
    # item is patches.Rectangle
    for item in data:
        height = item.get_height() # get Rectangle height
        # text(x, y, s, fontdict=None, withdash=<deprecated parameter>, **kwargs) s=show text
        plt.text(item.get_x(),height*1.05, height)
# ------------------
col_count = 3
A_scores = (553,536,548)
B_scores = (518,523,523)
C_scores = (613,570,588)
D_scores = (475,505,499)

index = np.arange(col_count)
bar_width = 0.2
# (x ,value) simple
# plt.bar(index, A_socres)
# bar(x, height, width=0.8透明度, bottom=None, *, align='center', data=None, **kwargs)[source]
# label:僅為涵義標示(與顯示無關)
A = plt.bar(index, 
        A_scores,
        bar_width,
        alpha=0.2,
        label="K1",
        )
B = plt.bar(index+0.2, 
        B_scores,
        bar_width,
        alpha=0.2,
        label="K2",
        )
C = plt.bar(index+0.4, 
        C_scores,
        bar_width,
        alpha=0.2,
        label="K3",
        )
D = plt.bar(index+0.6, 
        D_scores,
        bar_width,
        alpha=0.2,
        label="K4",
        )
#print(index)
createLabel(A)
createLabel(B)
createLabel(C)
createLabel(D)
# ------------------
plt.grid(True)
plt.xlabel("Subjext")     # show x label
plt.ylabel("Mean score")  # show y label
#print(np.arange(0, 3)+0.3)
# x 標示
plt.xticks(np.arange(0, 3)+0.3, ["Math", "Reading", "Scilent"])
# 加入圖例 plt.legend(title = "Court") 
plt.legend()
# xlim((left, right), left, right = xlim() - return the current xlim
plt.xlim(right=3.5) # x 顯示範圍
# ylim(bottom, top), bottom, top = ylim()  - return the current ylim
plt.ylim(top=700) # y 顯示範圍
plt.show()


# 1st sample
import matplotlib.pyplot as plt
# plot([x], y, [fmt], *, data=None, **kwargs)
# plot([x], y, [fmt], [x2], y2, [fmt2], ..., **kwargs)
# fmt = '[marker][line][color]/[color][marker][line]' format(color,linestyle .. ) -  'ro' for red circles
# set 畫線座標值, set y , x default auto from 0(offset 1)
plt.plot([5, 15, 20, 25])
# set 畫線座標值, set y and x
plt.plot([1, 2, 3, 4], [1, 4, 9, 16], 'ro')
plt.ylabel('some numbers')	# set Y軸 標示
plt.show()	# display a figure

# draw 3 lines
import matplotlib.pyplot as plt
import numpy as np 
# 0 to 5 step 0.2
t=np.arange(0., 5., 0.2)
print(t)
# draw 3 lines
plt.plot(t, t, 'r--', t, t**2, 'bs', t, t**3, 'g^')
plt.show()

# pyplot scatter(條件式畫圖)
import matplotlib.pyplot as plt
import numpy as np
# ------------------
data = {'a': np.arange(50),
        'c': np.random.randint(0, 50, 50),
        'd': np.random.randn(50)}
data['b'] = data['a'] + 10 * np.random.randn(50)
data['d'] = np.abs(data['d']) * 100
# ------------------
# scatter(x, y, s=None, c=None, marker=None, cmap=None, norm=None, vmin=None, vmax=None, alpha=None, linewidths=None, verts=None,
# 		 edgecolors=None, *, plotnonfinite=False, data=None, **kwargs)[source]
# s : scalar or array_like, shape (n, ), optional - The marker size in points**2. Default is rcParams['lines.markersize'] ** 2.
# c : color, sequence, or sequence of color, optional
plt.scatter('a', 'b', c='c', s='d', data=data)
plt.xlabel('entry a')
plt.ylabel('entry b')
plt.show()

# 多圖表(subplot)+統計圖(bar,scatter,plot)
import matplotlib.pyplot as plt
names = ['group_a', 'group_b', 'group_c']
values = [1, 10, 100]
# create figure : width, height in inches
plt.figure(figsize=(9, 3)) # 9inchs * 3inches
# plt.figure() # 640*480
# Add a subplot to the current figure
# nrows, ncols, position
plt.subplot(131)
# Make a bar plot(長條圖)
plt.bar(names, values)
# position #2 畫點
plt.subplot(132)
plt.scatter(names, values)
# position #2 畫折線圖
plt.subplot(133)
# plt.plot(names, values, linewidth=2.0) # change line width
plt.plot(names, values)
# 畫中間抬頭
plt.suptitle('Categorical Plotting')
plt.show()

# 多圖表(subplot)+多lines(plt.plot(t1, f(t1), 'bo', t2, f(t2), 'k'))
import matplotlib.pyplot as plt
import numpy as np
# ---------------
def f(t):
    return np.exp(-t) * np.cos(2*np.pi*t)
# ---------------
t1 = np.arange(0.0, 5.0, 0.1)
t2 = np.arange(0.0, 5.0, 0.02)
# 繪多line
plt.figure()
plt.subplot(211)
# draw 2 line 
plt.plot(t1, f(t1), 'bo', t2, f(t2), 'k')
# cosine wave
plt.subplot(212)
plt.plot(t2, np.cos(2*np.pi*t2), 'r--')
plt.show()

# 直方圖(histogram)-hist +  show text at figure
import matplotlib.pyplot as plt
import numpy as np
# ------------------
mu, sigma = 100, 15
x = mu + sigma * np.random.randn(10000)
# hist(x, bins=None, range=None, density=None, weights=None, cumulative=False, bottom=None, 
#      histtype='bar', align='mid', orientation='vertical', rwidth=None, log=False, color=None, label=None, stacked=False, normed=None, *, data=None, **kwargs)[source]
# n, bins, patches = plt.hist(x, 50, density=1, facecolor='g', alpha=0.75)
#  bins = 50 共有幾條條狀圖, facecolor:color, alpha:透明度, density:是否將得到的直方圖向量歸一化
plt.hist(x, 50, facecolor='g', alpha=0.75)
# title
plt.xlabel('Smarts')
plt.ylabel('Probability')
plt.title('Histogram of IQ')
# show text at figure(依座標) 
plt.text(60, 500, r'$\mu=100,\ \sigma=15$')
# show 格線
plt.grid(True)
plt.show()

# ========= set style ========
# all available style 
plt_themes = plt.style.available
print(plt_themes)
# set style 
# plt.style.use(plt_themes[2])

# ============ 設定說明 ========
# 設定中文字型
from matplotlib.font_manager import FontProperties
myfont = FontProperties(fname="c:/Windows/Fonts/msjh.ttc") #設定字型位置
plt.xlabel("鋒衛位置", fontproperties=myfont)   # X 軸說明
plt.ylabel("球員人數", fontproperties=myfont)   # Y 軸說明
plt.title("反映當時為了抗衡其他具有主宰力中前鋒的隊伍之現象", fontproperties=myfont) # 主標題
plt.suptitle("前場球員為芝加哥公牛隊的大宗", fontproperties=myfont) # 次標題
plt.xticks(range(0, 5), ["中鋒", "大前鋒", "小前鋒", "控球後衛", "得分後衛"], fontproperties=myfont) # 條圖說明

# ====== 加圖上說明 ====== 
# enumerate參數為可遍歷/可叠代的對象(如列表、字符串)
# lst = [1,2,3,4,5,6]
# for index,value in enumerate(lst):
#   print (‘%s,%s‘ % (index,value))
for i, v in enumerate(pos):
  plt.text(i-0.1 , v + 0.4, "{:.1f}".format(v))

# ====== 加入水平線 + 陰影 ====== 
# 10. pandas 模組作圖--長條圖（bar chart） 2nd --> 1st plot line
# 設定水平線
avg_pts = pp_stats["pts"].mean() # 生涯均值
plt.axhline(y = avg_pts, color="g", ls="--", alpha = 0.5) # 水平線
# 設定水平線至上方縣 陰影
plt.fill_between(pp_stats.index, avg_pts, pp_stats["pts"], 
                 where=pp_stats["pts"] >= avg_pts, color="gray",
                 alpha=0.5, interpolate=True) # 陰影

# ====== 調整座標軸 =====
# 10. pandas 模組作圖--長條圖（bar chart） 2nd --> 1st plot line
# 調整 X,Y 軸顯示範圍
plt.xlim(pp_stats.index.min(), pp_stats.index[14]) # 調整軸的範圍
plt.ylim(15, 30) # 調整軸的範圍

# ====== 調整刻度線與刻度線標籤 =====
plt.xticks(range(0, 5), ["中鋒", "大前鋒", "小前鋒", "控球後衛", "得分後衛"], fontproperties=myfont) # 條圖說明
plt.yticks(range(1, 5), range(11,15))
plt.xlabel("Positions")
plt.ylabel("Number of Players")

# ===== 加入圖例 =====
# plt.legend 要加在後面,才會 show 出來
bar_1 = pos.loc[["SG", "PG"]].values
bar_2 = pos.loc[["SF", "PF", "C"]].values
# 若包容多內容設定方法
# bar_1 = pos["Player"].loc[["SG", "PG"]].values
# bar_2 = pos["Player"].loc[["SF", "PF", "C"]].values
plt.bar(range(1, 3), bar_1, label="Back Court", alpha=0.6, color="red")
plt.bar(range(3, 6), bar_2, label="Front Court", alpha=0.6, color="green")
plt.legend(title = "Court") # 加入圖例

# ==== 繪製重疊的直方圖 ====
nba_salary = get_nba_salary()
nba_salary[nba_salary["position"] == "Point Guard"]["salary"].plot.hist(bins = 15, label = "PG")
nba_salary[nba_salary["position"] == "Shooting Guard"]["salary"].plot.hist(bins = 15, label = "SG")
nba_salary[nba_salary["position"] == "Guard"]["salary"].plot.hist(bins = 15, label = "G")
nba_salary[nba_salary["position"] == "Small Forward"]["salary"].plot.hist(bins = 15, label = "SF")
nba_salary[nba_salary["position"] == "Power Forward"]["salary"].plot.hist(bins = 15, label = "PF")
nba_salary[nba_salary["position"] == "Center"]["salary"].plot.hist(bins = 15, label = "C")
plt.legend() # 加入圖例

# ===== 繪製重疊的線圖(line graph) =====
nba_salary = get_nba_salary()
nba_salary[nba_salary["position"] == "Point Guard"]["salary"].plot.line(label = "PG")
nba_salary[nba_salary["position"] == "Shooting Guard"]["salary"].plot.line(label = "SG")
nba_salary[nba_salary["position"] == "Guard"]["salary"].plot.line(label = "G")
nba_salary[nba_salary["position"] == "Small Forward"]["salary"].plot.line(label = "SF")
nba_salary[nba_salary["position"] == "Power Forward"]["salary"].plot.line(label = "PF")
nba_salary[nba_salary["position"] == "Center"]["salary"].plot.line(label = "C")
plt.legend() # 加入圖例

# === 棒棒糖圖（Lollipop）===
# show 點
plt.plot(pos, range(1, pos.size + 1), 'o')
# show 線
# 畫水平線 axhline(y=0, xmin=0, xmax=1, **kwargs)[source]
plt.hlines(y=range(1, points_per_game.size + 1), xmin=0, xmax=pos, color='skyblue')
# show y 
plt.yticks(range(1, pos.size + 1), pos.index)
# x 軸 範圍
plt.xlim(0, 5)
```

## Seaborn
Seaborn 本質上是一個基於 matplotlib 庫的高級 API。它包含更適合處理圖表的默認設置。此外，還有豐富的可視化庫，包括一些複雜類型，如時間串行、聯合分佈圖（jointplots）和小提琴圖（violin diagrams）
```python
# 密度圖（Density plot）
%matplotlib inline 
import matplotlib.pyplot as plt
import seaborn as sns
nba_salary = get_nba_salary()
sns.kdeplot(nba_salary['salary'], shade=True)
plt.show()

# 密度圖（Density plot）- 重疊
# get only top 100 player more clear
nba_salary = get_nba_salary()
salary_pos = nba_salary.pivot(index='player', columns='position', values='salary')
colors = ["r", "g", "b", "c", "m","r" , "g", "b"]
print(salary_pos)
# get any position 1 item
positions = nba_salary["position"].unique()
print(positions)
for color, pos in zip(colors, positions):
    # notna() : not include NaN
    sns.kdeplot(salary_pos[pos][salary_pos[pos].notna()], shade=True, color=color, alpha = 0.5)

# ====== 小提琴圖 ========
# get only top 100 player more clear
nba_salary = get_nba_salary()
sns.violinplot(x=nba_salary["position"], y=nba_salary["salary"])

# 熱力圖(heatmap)
%matplotlib inline 
import numpy as np
import seaborn as sns
# ---------------------------
# rand() 僅正值
uniform_data = np.random.rand(10, 12)
# randn() 含正負值
normal_data = np.random.randn(10, 12)
# seaborn.heatmap(data, vmin=None, vmax=None, cmap=None, center=None, robust=False, annot=None, fmt='.2g', 
#   annot_kws=None, linewidths=0, linecolor='white', cbar=True, cbar_kws=None, cbar_ax=None, square=False, 
#   xticklabels='auto', yticklabels='auto', mask=None, ax=None, **kwargs)
#  annot = True ,write the data value in each cell.
#  fmt = string format
#  linewidths = Width of the lines that will divide each cell
#  cmap : map to different color
#  cbar=False Don’t draw a colorbar
# -- change color range --
#* ax = sns.heatmap(uniform_data, vmin=0, vmax=1)
# -- 色系中間為 0 --
#* ax = sns.heatmap(normal_data, center=0)
# -- load 1 file for test --
# load .csv file from https://github.com/mwaskom/seaborn-data
flights = sns.load_dataset("flights")
# DataFrame.pivot(index=None, columns=None, values=None)
# index=month columns=year values=passengers
flights = flights.pivot("month", "year", "passengers")
#* ax = sns.heatmap(flights)
#* ax = sns.heatmap(flights, annot=True, fmt='d')
#* ax = sns.heatmap(flights,linewidths=.5, cmap="YlGnBu")
ax = sns.heatmap(flights, center=flights.loc["June", 1955], cbar=False)
```

## bokeh(draw by HTML)
conda install bokeh  
from bokeh.plotting import figure, show  
> ===== 其他圖形 =====  
> bokeh.charts.Bar — 製作長條圖  
> bokeh.charts.BoxPlot — 製作盒鬚圖  
> bokeh.charts.HeatMap — 製作熱圖  
> bokeh.charts.Donut — 製作甜甜圈圖  
> ===== Bokeh 也提供了排版專用的工具 =====  
> Horiontal Layout / 水平式版面 ( hplot )  
> Vertical Layout / 垂直式版面 ( vplot )  
> Grid Layout / 格式排版 ( gridplot )  
> Form Layout / 表單排版 (formplot )  

function     	| 說明
-------------	|------
p = figure() 	|設繪圖板大小
p.circle() 		|畫圓
p.line() 		|畫線
p.multi_line()	|multi line
p.vbar() 		|bar(長條圖)
p.patches() 	|patch(多邊形)
show(p)			|最後畫圖

```python
# draw by HTML
from bokeh.plotting import figure, show, output_file
# 設定輸出檔名
output_file("out.html")
# 設繪圖板大小
p = figure(plot_width=500, plot_height=500)
x = [1,2,3,4,5,6,7,8,9,10,11]
y = [6,3,7,2,4,6,1,2,3,5,6]
# 畫圓
p.circle(x, y, size=20, color="gray", alpha=0.6)
# 畫線
p.line(x, y, line_width=3)
# multi line
x1 = [1, 2, 3]
x2 = [2, 3, 4, 5, 6]
y1 = [3, 2, 5]
y2 = [3, 2, 4, 1, 3]
p.multi_line([x1,x2] , [y1, y2],
             color=["firebrick", "navy"], alpha=[0.8, 0.3], line_width=5)
# bar(長條圖)
p.vbar(x=[1, 2, 3, 4], width=0.5, bottom=0,
       top=[1.2, 2.5, 3.7, 2.9], color="black",alpha=0.4)

# patch(多邊形)
x1 = [1, 4, 5, 2]
x2 = [3, 4, 5, 6]
x3 = [1,3,2]
y1 = [2, 3, 5, 6]
y2 = [4, 7, 7, 5]
y3 = [7,8,5.5]
p.patches([x1,x2,x3 ], [y1,y2,y3],
          color=["black", "navy","firebrick"], alpha=[0.2, 0.2,0.3], line_width=2)
show(p)
```

## base plotting system

## ggplot2


# Warning 

## No module named 'sklearn.cross_validation'
```python
# cross_validatio不再使用了,劃分到 model_selection
from sklearn.model_selection
```


# 分析

## sklearn
```python
# 取測試資料
# model_selection中train_test_split()函式
# X_train, X_test, y_train, y_test = train_test_split(train_data, train_target, test_size, random_state，shuffle)
# train_data：待劃分的樣本資料
# train_target：待劃分的對應樣本資料的樣本標籤
# test_size：1）浮點數，在0 ~ 1之間，表示樣本佔比（test_size = 0.3，則樣本資料中有30%的資料作為測試資料，記入X_test，其餘70%資料記入X_train，同時適用於樣本標籤）；
#            2）整數，表示樣本資料中有多少資料記入X_test中，其餘資料記入X_train
# random_state：隨機數種子，種子不同，每次採的樣本不一樣；種子相同，採的樣本不變（random_state不取，取樣資料不同，但random_state等於某個值，取樣資料相同，取0的時候也相同，這可以自己程式設計嘗試下，不過想改變數值也可以設定random_state = int(time.time())）
# shuffle：洗牌模式，
#            1）shuffle = False，不打亂樣本資料順序；2）shuffle = True，打亂樣本資料順序
# --------------
# from sklearn.model_selection import train_test_split
# train_df, validation_df = train_test_split(labeled_df, test_size=0.3, random_state=123)

# model_selection中train_test_split 2nd example
import numpy as np
from sklearn.model_selection import train_test_split
X, y = np.arange(30).reshape((10, 3)), range(10) 
X_train, X_test ,y_train, y_test= train_test_split(X, y,test_size=0.3, random_state = 20, shuffle=True)
```

## 均方誤差（Mean Square Error）


# API or url

## 1.stock information
```
// 某月份某檔股票資料
https://www.twse.com.tw/exchangeReport/STOCK_DAY?response=html&date=20130501&stockNo=1423
https://www.twse.com.tw/exchangeReport/STOCK_DAY?response=json&date=20130501&stockNo=1423
// csv download
https://www.twse.com.tw/exchangeReport/STOCK_DAY?response=csv&date=20130501&stockNo=1423
// 上市
http://www.tpex.org.tw/web/stock/aftertrading/daily_trading_info/st43_result.php?d=107/08&stkno=3105
```

# tool

## 1. python2 to python3

```
// C:\Users\RobertKao\AppData\Local\Programs\Python\Python37\Tools\scripts\2to3
#會產生一個script.py -> Python3 script.py.bak -> Python2
2to3 -w script.py
```  

# example

## 1. get title

```python
import requests
from bs4 import BeautifulSoup
r = requests.get("https://www.ptt.cc/bbs/MobileComm/index.html") # get page
# print(r.text) # print HTML

soup = BeautifulSoup(r.text, "html.parser") # parser by html format
sel = soup.select("div.title a") # get <div class="title"></div>'s <a>'
# print(sel)

# print href and title
for s in sel:
    print(s["href"], s.text)
```

**send cookie for over 18 + file access**
```python
import requests
from bs4 import BeautifulSoup

# prepare get cookie
r = requests.session()
# set payload data
payload = {
    "from":"/bbs/Gossiping/index.html",
    "yes":"yes"
}
r1 = r.post("https://www.ptt.cc/ask/over18?from=%2Fbbs%2FGossiping%2Findex.html", payload)
r2 = r.get("https://www.ptt.cc/bbs/Gossiping/index.html")

soup = BeautifulSoup(r2.text, "html.parser") # parser by html format
sel = soup.select("div.title a") # get <div class="title"></div>'s <a>'

# file access
# flag : r/w/b(binary)/a(add)
f = open("file.txt", "w")

# print href and title
for s in sel:
    print(s["href"], s.text)
    # file write
    f.write(str(s["href"]) + s.text + "\n")

# file close
f.close()

print("dump file ...")
# file open
f = open("file.txt", "r")
rf = f.read()
print(rf)
# file close
f.close()
```

## 2. get page up

```python
import requests
from bs4 import BeautifulSoup
url = "https://www.ptt.cc/bbs/MobileComm/index.html"
for i in range(3):
    r = requests.get(url) # get
    soup = BeautifulSoup(r.text, "html.parser") # parser html
    sel = soup.select("div.title a") # get <div class="title"></div>'s <a>'
    u = soup.select("div.btn-group.btn-group-paging a") # get <div class="title"></div>'s <a>'
    print("page", i,":" , url)
    for s in sel:
        print(s["href"], s.text)
    url = "https://www.ptt.cc" + u[1]["href"] # get 2nd(up page) href
```

## 3. get picture

```python
import requests

# get image 
pic = requests.get("https://imgur.dcard.tw/N2k5kV2.jpg")
# open file
f = open("img1.png", "wb")
# write image content to file
f.write(pic.content)
f.close()

print("save image ...")
```

## 4. get mutiple picture

```python
import requests
from bs4 import BeautifulSoup
import json

# open file for log
test = open("spider/pet/test.txt","w",encoding='UTF-8')

# get page
p = requests.Session() # request include get cookie
url = requests.get("https://www.dcard.tw/f/pet") # get
soup = BeautifulSoup(url.text, "html.parser") # parser html
# print(soup)

# get search item link
sel = soup.select("div.PostListPage_topicListWrapper_Iw1Nao a.TopicList_topic_1XGOjs")
a = []
query_data = sel[2].text # get text --> 貓
# print(query_data, "...")
for s in sel:
    # print(s["href"])
    a.append(s["href"])

# search a[2] : 貓 page
# url = "https://www.dcard.tw" + a[2]
# print(url) # show page link address

# params
post_data={
    "field":"topics",
    "query": query_data,
    "sort":"created",
    "offset":"30",
    "since":"0"
}

'''
headers : can not add
head_data = { "Referer": "https://www.dcard.tw/", "User-Agent": "Mozilla/5.0" }
r = p.get("https://www.dcard.tw/_api/search/posts", params=post_data, headers=head_data)
'''

# show page 0 to 1 title
for k in range(0,2):
    # print("page ", k)
    post_data["offset"] = str(k*30)
    r = p.get("https://www.dcard.tw/_api/search/posts", params=post_data)
    # json to text 
    data2 = json.loads(r.text)
    for u in range(len(data2)):
        temp_url = "/f/pet/p/" + str(data2[u]["id"]) + "-"+ data2[u]["title"].replace(" ","-")
        a.append(temp_url)

# save and show all page link address
j=0
q=0
for i in a[2:]:
    url = "https://www.dcard.tw"+i
    j+=1
    print ("第",j,"頁的URL為:"+url)
    test.write("第 {} 頁的URL為: {} \n".format(j,url))
    url=requests.get(url)
    soup = BeautifulSoup(url.text,"html.parser")
    sel_jpg = soup.select("div.PostPage_content_1JHbeJ div div img.GalleryImage_image_3lGzO5")
    # save and show all image
    for c in sel_jpg:
        # check include "https" is correct address
        if ( "https" in c["src"] ):
            q+=1
            print("第",q,"張:",c["src"])
            test.write("%\n""第 {} 張: {} \n".format(q,c["src"]))
            # get image and write
            pic = requests.get(c["src"])
            f = open("spider/pet/" + str(q) + ".png", "wb")
            f.write(pic.content)
            f.close()

test.close()
print(".....end")
```

## 5. get mutiple movie information by selenium

```python
from pyquery import PyQuery
from selenium import webdriver

# give movie information
def get_movie_info(movie_url):
    """
    get movie info from IMDB
    """
    # pyquery 解析
    d = PyQuery(movie_url)
    movie_rating = float(d("strong span").text())
    movie_genre = [x.text() for x in d(".subtext a").items()]
    movie_release_date = movie_genre.pop()
    movie_poster = d(".poster img").attr("src")
    movie_cast = [x.text() for x in d(".primary_photo+ td a").items()]
    
    """
    print(movie_rating)
    print(movie_genre)
    print(movie_release_date)
    print(movie_poster)
    print(movie_cast)
    print(d)
    """
    movie_info = {
        "movieRating" : movie_rating,
        "movieGenre" : movie_genre,
        "movieReleaseDate" : movie_release_date,
        "moviePosterLink" : movie_poster,
        "movieCast" : movie_cast,
    }
    return movie_info;

def get_movies(*args):
    """
    get multiple movie
    """
    # open web
    imdb_home = "https://www.imdb.com"
    driver = webdriver.Chrome('./chromedriver')  # Optional argument, if not specified will search path.
    
    movies = dict()
    for movie_title in args:
        # to home
        driver.get(imdb_home)
        # find search itel
        search_elem = driver.find_element_by_xpath("//input[@id='navbar-query']")
        search_elem.send_keys(movie_title)
        # click() search
        driver.find_element_by_xpath("//button[@id='navbar-submit-button']").click()
        # click 1st movie
        driver.find_element_by_xpath("//tr[@class='findResult odd'][1]/td[@class='primary_photo']/a").click()
        # get movie info
        movie_info = get_movie_info(driver.current_url)
        movies[movie_title] = movie_info
        
    # close browse
    driver.close()
    return movies

# show movie information
# return_msg = get_movie_info("https://www.imdb.com/title/tt4154796")
# print(return_msg)

# show multiple movie information
movie_msg = get_movies("Avengers: Endgame", "Captain Marvel")
print(movie_msg)
```

## 6. stock high price list

```python
import requests
from bs4 import BeautifulSoup
import pandas
import datetime

# hot stock for listed company
# e=tse, otc
def get_hot_stock():
    stock_types = ["tse", "otc"]
    stock_list = ["https://tw.stock.yahoo.com/d/i/rank.php?t=pri&e={}&n=100".format(st) for st in stock_types]
    current_dt = datetime.datetime.now().strftime("%Y-%m-%d %X")
    current_dts = [current_dt for _ in range(200)]
    ids = []
    names = []
    prices = []
    amounts = []
    mkt_values = []
    
    for get_url in stock_list:
        r = requests.get(get_url)
        soup = BeautifulSoup( r.text, "html.parser") # parser by html format
        sel = soup.select("tr tbody tr")
        for i in range(len(sel)):
            if i<=1:
                continue
            row_data = sel[i].text.split()
            ids.append(row_data[1])
            names.append(row_data[2])
            prices.append(float(row_data[3]))
            amounts.append(int(row_data[9].replace(",", "")))
            mkt_values.append(float(row_data[10])*100000000)
    types = ["上市" for i in range(100)] + ["上櫃"for i in range(100)]
    ky_regists = [True if "KY" in st else False for st in names]
    
    # 打包
    df = pandas.DataFrame()
    df["scrapingTime"] = current_dts
    df["type"] = types
    df["kyRegistered"] = ky_regists
    df["ticker"] = ids
    df["stock"] = names
    df["price"] = prices
    df["volume"] = amounts
    df["mktValue"] = mkt_values
    return df

# dump hot stock
price_ranks = get_hot_stock()
print(price_ranks.shape) # show rows × columns
# price_ranks.head() # show head 5
# price_ranks.tail() # show tail 5
price_ranks # middle show ...
```

## 7. flask get data(web api)
http://127.0.0.1:5000  
http://127.0.0.1:5000/cities/all  
```python
import flask
from flask import jsonify

app = flask.Flask(__name__)
app.config["DEBUG"] = True
# show chinese
app.config["JSON_AS_ASCII"] = False

# test data
tpe = {
"id": 0,
	"city_name": "台北",
	"country_name": "台灣",
	"is_capital": True,
	"location": {
		"longitude": 121.569649,
		"latitude": 23.03786
	}
}
nyc = {
	"id": 1,
	"city_name": "New York",
	"country_name": "United States",
	"is_capital": False,
	"location": {
		"longitude": -74.004364,
		"latitude": 40.710405
	}
}
ldn = {
	"id": 2,
	"city_name": "London",
	"country_name": "United Kingdom",
	"is_capital": True,
	"location": {
		"longitude": -0.114089,
		"latitude": 51.507497
	}
}
cities = [tpe, nyc, ldn]

@app.route('/', methods=['GET'])
def home():
	return "<h1>Hello Flash</h1>"

@app.route('/cities/all', methods=['GET'])
def city_all():
	return jsonify(cities)

app.run()
```

## 7. flask get data(web api-get csv file data)
http://127.0.0.1:5000  
http://127.0.0.1:5000/gapminder/all  
```python
import flask
from flask import jsonify
import pandas

app = flask.Flask(__name__)
app.config["DEBUG"] = True
# show chinese
app.config["JSON_AS_ASCII"] = False

# get gapminder csv
pd = pandas.read_csv('./gapminder.csv') 
gapminder_data = pd.get_values() # get csv data

gapminder_list = []
row_no = int(pd.shape[0])
column_no = int(pd.shape[1])
for i in range(row_no):
	row_dict = {}
	for j in range(column_no):
		row_dict[pd.columns[j]] = gapminder_data[i][j]
	gapminder_list.append(row_dict)

@app.route('/', methods=['GET'])
def home():
	return "<h1>Hello Flash</h1>"

@app.route('/gapminder/all', methods=['GET'])
def gapminder_all():
	return jsonify(gapminder_list)

app.run()
```

## 8. flask get data(web api-get csv file for specific country)
http://127.0.0.1:5000  
http://127.0.0.1:5000/gapminder/all  
http://127.0.0.1:5000/gapminder?country=Taiwan  
http://127.0.0.1:5000/gapminder?country=Austria  
```python
import flask
# add request for get parameter
from flask import jsonify,request
import pandas

app = flask.Flask(__name__)
app.config["DEBUG"] = True
# show chinese
app.config["JSON_AS_ASCII"] = False

# get gapminder csv
pd = pandas.read_csv('./gapminder.csv') 
gapminder_data = pd.get_values() # get csv data

gapminder_list = []
row_no = int(pd.shape[0])
column_no = int(pd.shape[1])
for i in range(row_no):
	row_dict = {}
	for j in range(column_no):
		row_dict[pd.columns[j]] = gapminder_data[i][j]
	gapminder_list.append(row_dict)

@app.route('/', methods=['GET'])
def home():
	return "<h1>Hello Flash</h1>"

@app.route('/gapminder/all', methods=['GET'])
def gapminder_all():
	return jsonify(gapminder_list)

# get specific country
@app.route('/gapminder', methods=['GET'])
def gapminder_country():
	if 'country' in request.args:
		country = request.args['country']
	else:
		return "Error: No country provided. Please specify a country."

	results = []
	for elem in gapminder_list:
		if elem['country'] == country:
			results.append(elem)
	return jsonify(results)

app.run()
```

## 9. firebase test
// install firebase_admin(conda not support  
pip install firebase_admin  
```python
import firebase_admin
from firebase_admin import credentials

from firebase_admin import db
from requests import get

#init firebase
cred = credentials.Certificate("./my-pythone-test-db-firebase-adminsdk-hshx2-1cad43354a.json")
firebase_admin.initialize_app(cred, {
    'databaseURL' : 'https://my-pythone-test-db.firebaseio.com/' # 替換成自己的 Firebase 網址
})

# get json file
json_url = 'https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.json'
chicago_bulls_dict = get(json_url).json()

# add data to DB
root = db.reference()
root.child('chicago_bulls').push(chicago_bulls_dict)

# get data from DB
ref = db.reference('chicago_bulls')
chicago_bulls = ref.get()
chicago_bulls
```

## 10. pandas 模組作圖--長條圖（bar chart）
plot.bar()
```python
# Series show bar
import pandas as pd
import matplotlib.pyplot as plt
# ------------------
csv_url = "https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.csv"
df = pd.read_csv(csv_url)
grouped = df.groupby("Pos")
pos = grouped["Pos"].count()
# Series show bar
# Series.plot.bar(self, x=None, y=None, **kwargs)[source]
pos.plot.bar()
# show y tick location : yticks(ticks, [labels], **kwargs) 
plt.yticks([1, 2, 3, 4], [1, 2, 3, 4])
plt.show()

# show group 平均值圖
%matplotlib inline 
import pandas as pd
import matplotlib.pyplot as plt
# ------------------
play_info_url = "https://storage.googleapis.com/ds_data_import/chicago_bulls_1995_1996.csv"
per_game_url = "https://storage.googleapis.com/ds_data_import/stats_per_game_chicago_bulls_1995_1996.csv"
play_info = pd.read_csv(play_info_url)
per_game = pd.read_csv(per_game_url)
# merge play_info and per_game 
play_info_mix = play_info.merge(per_game, left_on='Player', right_on='Name' )
# group by Pos
grouped = play_info_mix.groupby("Pos")
# group "PTS/G" mean(平均值)
# print(grouped["PTS/G"].mean())
pos_pstg_mean = grouped["PTS/G"].mean()
print(pos_pstg_mean)
# plot by bar
pos_pstg_mean.plot.bar()
plt.show()
```

## 11. pandas 模組作圖--直方圖（bar histogram)
```python
# NBA 薪水分布圖
%matplotlib inline 
import requests
from bs4 import BeautifulSoup
import pandas as pd
import matplotlib.pyplot as plt

def get_nba_salary():
    # chaget to post + payload get morether 100
    payload = {
        "ajax":"true",
        "mobile":"false"
    }
    # r = requests.get("https://www.spotrac.com/nba/rankings/") # only get 100 items
    r = requests.post("https://www.spotrac.com/nba/rankings/", payload)
    # get(text format) parser
    soup = BeautifulSoup(r.text, "html.parser") # parser by html format
    # select process
    salarys = [p.text.replace(",", "") for p in soup.select("td.rank-value span.info")]
    salarys = [int(p.replace("$", "")) for p in salarys]
    players = [p.text for p in soup.select("td.rank-name h3 a")]
    positions =  [p.text for p in soup.select("td.rank-name span.rank-position")]
    # print(salary)
    # print(player)
    # print(position)
    df = pd.DataFrame()
    df["player"] = players
    df["position"] = positions
    df["salary"] = salarys
    return df

nba_salary = get_nba_salary()
# print(nba_salary)
# bins 表 共有幾條條狀圖
plt.hist(nba_salary["salary"], bins=15)
plt.show()
```

## 12. pandas 模組作圖--盒鬚圖（box-and-whisker plot）
```python
# NBA 薪水 盒鬚圖（box-and-whisker plot）- 外部的圓圈為離群值
# %matplotlib inline 
import requests
from bs4 import BeautifulSoup
import pandas as pd
import matplotlib.pyplot as plt

def get_nba_salary():
    # chaget to post + payload get morether 100
    payload = {
        "ajax":"true",
        "mobile":"false"
    }
    # r = requests.get("https://www.spotrac.com/nba/rankings/") # only get 100 items
    r = requests.post("https://www.spotrac.com/nba/rankings/", payload)
    # get(text format) parser
    soup = BeautifulSoup(r.text, "html.parser") # parser by html format
    # select process
    salarys = [p.text.replace(",", "") for p in soup.select("td.rank-value span.info")]
    salarys = [int(p.replace("$", "")) for p in salarys]
    players = [p.text for p in soup.select("td.rank-name h3 a")]
    positions =  [p.text for p in soup.select("td.rank-name span.rank-position")]
    # print(salary)
    # print(player)
    # print(position)
    df = pd.DataFrame()
    df["player"] = players
    df["position"] = positions
    df["salary"] = salarys
    return df

nba_salary = get_nba_salary()
#show group count
# grouped = nba_salary.groupby("position").count()
# print(grouped)

# show all position + salary
#for i in range(nba_salary.shape[0]):
#    print('{0:14}-{1:9}'.format(nba_salary.values[i][1], nba_salary.values[i][2]))

# 盒鬚圖（box-and-whisker plot）是資料科學團隊慣常用作探索一組數值資料依類別分組的分佈情況之圖形，
# 藉著圖形可以觀察不同類別分組數值資料的峰度（kurtosis）以及偏態（skewness）
# 資料整理 依行填值
# Return reshaped DataFrame organized by given index / column values
# DataFrame.pivot(index=None, columns=None, values=None)
box_df = nba_salary.pivot(index='player', columns='position', values='salary')
# print(box_df)
# Make a box plot of the DataFrame columns.
box_df.plot.box()
plt.show()
```

## 13. pandas 模組作圖--散佈圖（scatter plot）
```python
# NBA 薪水-得分 散佈圖（scatter plot）
# 因資料的關係,僅有部分球員
%matplotlib inline 
from pyquery import PyQuery as pq
from requests import get
import pandas as pd
import matplotlib.pyplot as plt
import requests
from bs4 import BeautifulSoup
# read json
import json

def get_nba_salary():
    # chaget to post + payload get morether 100
    payload = {
        "ajax":"true",
        "mobile":"false"
    }
    # r = requests.get("https://www.spotrac.com/nba/rankings/") # only get 100 items
    r = requests.post("https://www.spotrac.com/nba/rankings/", payload)
    # get(text format) parser
    soup = BeautifulSoup(r.text, "html.parser") # parser by html format
    # select process
    salarys = [p.text.replace(",", "") for p in soup.select("td.rank-value span.info")]
    salarys = [int(p.replace("$", "")) for p in salarys]
    players = [p.text for p in soup.select("td.rank-name h3 a")]
    positions =  [p.text for p in soup.select("td.rank-name span.rank-position")]
    df = pd.DataFrame()
    df["player"] = players
    df["position"] = positions
    df["salary"] = salarys
    return df

def get_pts_game():
  """
  Get NBA players' PTS/G from NBA.com
  """
  # nba_stats_url = "https://stats.nba.com/stats/leagueLeaders?LeagueID=00&PerMode=PerGame&Scope=S&Season=2017-18&SeasonType=Regular+Season&StatCategory=PTS"
  # pts_game_dict = get(nba_stats_url).json()
  # read json(sometimes get error --> chaneg to read file)
  with open("pts_game.json") as json_file:
    pts_game_dict = json.load(json_file)
  players = [pts_game_dict["resultSet"]["rowSet"][i][2] for i in range(len(pts_game_dict["resultSet"]["rowSet"]))]
  pts_game = [pts_game_dict["resultSet"]["rowSet"][i][22] for i in range(len(pts_game_dict["resultSet"]["rowSet"]))]
  df = pd.DataFrame()
  df["player"] = players
  df["pts_game"] = pts_game
  return df

nba_salary = get_nba_salary()
pts_game = get_pts_game()
df = pd.merge(nba_salary, pts_game)
# matplotlib.pyplot.scatter(x, y, s=None, c=None, marker=None, cmap=None, norm=None, vmin=None, vmax=None, alpha=None,
# linewidths=None, verts=None, edgecolors=None, *, plotnonfinite=False, data=None, **kwargs)
plt.scatter(df["pts_game"], df["salary"])
plt.show()
```

## 14. pandas 模組作圖--線圖（line graph）
```python
# Paul Pierce information - 線圖（line graph）
%matplotlib inline 
from pyquery import PyQuery as pq
import pandas as pd
import matplotlib.pyplot as plt
def get_pp_stats():
  """
  Get Paul Pierce stats from basketball-reference.com
  """
  stats_url = "https://www.basketball-reference.com/players/p/piercpa01.html"
  # pandas direct query url
  html_doc = pq(stats_url)
  # print(html_doc)
  pts_css = "#per_game .full_table .right:nth-child(30)"
  ast_css = "#per_game .full_table .right:nth-child(25)"
  reb_css = "#per_game .full_table .right:nth-child(24)"
  year = [str(i)+"-01-01" for i in range(1999, 2018)]
  # 得分,籃板,助攻
  pts = [float(p.text) for p in html_doc(pts_css)]
  ast = [float(a.text) for a in html_doc(ast_css)]
  reb = [float(r.text) for r in html_doc(reb_css)]
  df = pd.DataFrame()
  df["year"] = year
  df["pts"] = pts
  df["ast"] = ast
  df["reb"] = reb
  return df

pp_stats = get_pp_stats()
# pp_stats["year"] change to datetime mode
pp_stats["year"] = pd.to_datetime(pp_stats["year"] )
# change index to year field
# index 非 datetime 會密密疊在一起
pp_stats = pp_stats.set_index("year")

# draw line graph
# plt.plot(pp_stats["pts"])
# plt.plot(pp_stats["ast"])
# plt.plot(pp_stats["reb"])
# 更改為 line 繪圖
pp_stats.plot.line()
# 放置圖例說明
plt.legend(['PTS', 'REB', 'AST'], loc='upper right')
plt.show()
```

## 15. stock OHLC Candlestick
```python
# K線理論（Candlestick Charts）原意：蠟燭圖；又稱、蠟燭線、日本線、陰陽線、棒線、紅黑線
%matplotlib inline 
import requests
import datetime
import pandas as pd
import chart_studio.plotly as py
import plotly.graph_objs as go

def get_ohlc(twse_ticker):
  """
  Get ohlc data for current month
  """
  today = datetime.datetime.today().strftime('%Y%m%d')
  twse_url = "http://www.twse.com.tw/exchangeReport/STOCK_DAY?response=json&date={}&stockNo={}".format(today, twse_ticker)
  # 未加.json() 僅是 return value 
  stock = requests.get(twse_url).json()
  trading_dates = []
  dates = []
  opens = []
  highs = []
  lows = []
  closes = []
  for i in range(len(stock["data"])):
    trading_dates.append(stock["data"][i][0])
    opens.append(float(stock["data"][i][3]))
    highs.append(float(stock["data"][i][4]))
    lows.append(float(stock["data"][i][5]))
    closes.append(float(stock["data"][i][6]))

  # year 108 --> 2019
  for d in trading_dates:
    sub = d.split("/")
    dates.append("{}-{}-{}".format(int(sub[0])+1911, sub[1], sub[2]))

  df = pd.DataFrame()
  df["trading_date"] = dates
  df["open"] = opens
  df["high"] = highs
  df["low"] = lows
  df["close"] = closes
  df = df.set_index("trading_date")
  return df

tsmc = get_ohlc('2330')
# -- show Candlestick fig --
trace = go.Candlestick(x=tsmc.index,
                       open=tsmc["open"],
                       high=tsmc["high"],
                       low=tsmc["low"],
                       close=tsmc["close"])
# no show bottom fig
layout = go.Layout(
    xaxis = dict(
        rangeslider = dict(
            visible = False
        )
    )
)
fig = go.Figure(data=trace, layout=layout)
fig.show()

# update to plotly wibside(need API key)
py.sign_in('kyp001', 'bEtPpStSQgWRADCmGGe9') # Use your own plotly Username / API Key
py.iplot(fig, filename='simple_candlestick')
```

## 16. 艾姆斯房價（Imes, Iowa）資料分析  
https://www.kaggle.com/c/house-prices-advanced-regression-techniques  
```python
# get % train/test data 
import pandas as pd
from sklearn.model_selection import train_test_split
# ----------------
labeled_url = "https://storage.googleapis.com/kaggle_datasets/House-Prices-Advanced-Regression-Techniques/train.csv"
labeled_df = pd.read_csv(labeled_url)
train_df, validation_df = train_test_split(labeled_df, test_size=0.3, random_state=123)
print(train_df.shape)
print(validation_df.shape)


# 單變數的迴歸模型(相關性)
import pandas as pd
from sklearn.model_selection import train_test_split
# ---------------------
labeled_url = "https://storage.googleapis.com/kaggle_datasets/House-Prices-Advanced-Regression-Techniques/train.csv"
labeled_df = pd.read_csv(labeled_url)
df_corr = labeled_df.corr()
sale_price_corr = df_corr["SalePrice"].abs().sort_values(ascending=False)
print(sale_price_corr)

# GrLivArea(x) vs SalePrice(y)散佈圖（scatter plot）
%matplotlib inline
import pandas as pd
from sklearn.model_selection import train_test_split
import matplotlib.pyplot as plt
# --------------------------
labeled_url = "https://storage.googleapis.com/kaggle_datasets/House-Prices-Advanced-Regression-Techniques/train.csv"
labeled_df = pd.read_csv(labeled_url)
df_corr = labeled_df.corr()
sale_price_corr = df_corr["SalePrice"].abs().sort_values(ascending=False)
plt.scatter(labeled_df["GrLivArea"],labeled_df["SalePrice"])
plt.xlabel('GrLivArea')
plt.ylabel('SalePrice')
plt.show()
```