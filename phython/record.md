# phython record

*   [Root](../README.md)


# Install package

## 1. install by pipe

**upgrade pip**
```
python -m pip install --upgrade pip
```

**jupyter notebook**
coding tool
```
pip install jupyter notebook
```

**Python Requests**
對網路發動請求的套件，可實作對網頁做get、post等HTTP協定的行為
```
pip install requests
```

**Python Beautifulsoup4**
借助網頁的結構特性來解析網頁的工具，只需要簡單的幾條指令就可以提取HTML標籤裡的元素
```
pip install beautifulsoup4
```

## 2. install in linux

**python3**
```
// check install
apt list --installed | grep phython

// check version
python3 --version
```

**Anaconda**
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

**crontab(環型工作排程)-linux comman**

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

##4. Miniconda(輕量化版本的 Anaconda)
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
// which python 檢視可以發現系統已經改以 Miniconda 的 Python 作為預設。
conda install requests beautifulsoup4 pandas
```

##5. Django(創建 Web 應用程式和 Web API 的框架)##

##6. VsCode##
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

**HTML**
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

**XPath-XML Path Language**  
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

**CSS Selector**  
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
```

## 2. socket

**import pckage**
```python
import socket
```  


**function**
```python
socket.socket([family], [type] , [proto] )
```

# record

```python
// del - 將完成賦值的物件自環境中刪除
hello_msg = "Hello Python!"
print(hello_msg)
del hello_msg

// help() 函數查詢函數的說明文件
help(print)
```

**function**
```python
//type
print(type("xy"))
print(type(12))


```

**variable**
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
```

**collection**
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


**flow control**
```python
// if
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

# package

**datetime**
```python
import datetime
current_dt = datetime.datetime.now().strftime("%Y-%m-%d %X")
```

**BeautifulSoup4(selector 分析網頁)**

**beautifulsoup4 - 解析 HTML 資料**
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

**beautifulsoup4 - example**
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

**requests(抓網頁)**  
Requests是一個Python HTTP庫

**requests : disable SSL Warnings - json**
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

**requests : support SSL certificate verify - json**
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

**requests : html**
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


**nbextensions**
```python
// 代碼補全 for jupyter notebook(nbextensions) install
conda install -c conda-forge jupyter_contrib_nbextensions

点开 Nbextensions 的选项，并勾选 Hinterland
```

**pandas(資料分析)**  
Pandas 是 python 的一個數據分析 lib
```python
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
```


**lxml**  
lxml is the most feature-rich and easy-to-use library for processing XML and HTML in the Python language

**pyquery 解析 HTML 資料**  
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
```

**selenium-操控瀏覽器來擷取 HTML**  
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

**flask**
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
**flask-apy.py**
```python
import flask

app = flask.Flask(__name__)
app.config["DEBUG"] = True

@app.route('/', methods=['GET'])
def home():
        return "<h1>Hello Flask</h1>"
    
app.run()
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

## 7. flask get data
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
for i in range(10):
	print("...")
```
