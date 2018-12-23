# Resource List

*   [Root](../README.md)

### 1.google key
*	website template
*	網頁版型
*	github search 

### some key
*	transition  
*	animation  
*	jQuery  
*	JavaScript : 懂陣列、函數、物件操作後，就會再進一步投入中階語法  
*	HTML、CSS 還沒實際做出一個版型就想直接用 Bootstrap  
*	JavaScript 才剛會 變數、if、for 等基本語法，就想直接學 SPA 框架 (vue、react、angular)  
*	AJAX  
*	API 整合  
*	在瀏覽器的網頁上設計 2、3D 圖形動畫  
*	將訪客資訊記錄到瀏覽器上的資料庫  
*	Firebase‍   
*	D3、C3.JS  
*	Frontend Single Page Application（SPA）  
*	整合第三方 API、生命週期 (init、offline)  
*	共用的版型獨立成一個檔案，例如叫做 layout.php  
*	gulp 學一個樣版語言 -   
*	要用 CSS 框架，至少底層的 CSS3 media queries 瞭解響應式原理，你才知道當版型有超出預期的調整時，自己也能寫 CSS 去客製  
*	想學 JS SPA 框架，至少先把 AJAX 原理搞熟、知道網址 router 邏輯、JS執行生命週期再去碰才不會覺得各種觀念卡卡  
*	HTML、CSS 網頁版型是基礎功  
*	MVC 的抽象觀念  
*	D3 讓我對 SVG 底層更加透徹  
*	WebVR 使我對 WebGL、three.js 有更深入的瞭解  
* Ajax
* 程式語言進行優化 (gulp、Webpack、CSS 預處理器、NPM)
* 網頁元素的設計細節，例如 web font、image、loading、文字設定(行距、字距、粗細、字形大小、標題權重)

### 名詞
*	常見的framework
	```
	bootstrap，CSS，快速建造一個網站的畫面配置
	Ruby on Rails，Ruby，全端framework
	Nodejs+Express，Javascript，後端framework
	AngularJs，Javascript，前端framework
	Laravel，PHP，前後端framework
	```
* Restful API
	```
	REST : Resource Representational State Transfer
	如果我們在寫一隻商品的WebAPI，讓工程師隨便寫可能會有以下方式來作interface：
	獲得商品資料 GET   /getAllItems
	獲得商品資料 GET   /getItem/11
	新增商品資料 POST /createItem
	更新商品資料 POST  /updateItem/
	刪除商品資料 POST  /deleteItem/

	若是以使用 RESTful API 開發的話:
	獲取商品資料 /GET     /items
	獲取商品資料 /GET     /items/1
	新增商品資料 /POST   /items
	更新商品資料 /PATCH /items/1 
	刪除商品資料 /DELETE /items/1

	GET：取得(想要的服務)的資料或是狀態。（safe & idempotent）
	POST：新增一項資料。
	PUT：利用更新的方式於"指定位置"新增一項資料。 （idempotent）
	PATCH：在現有的資料欄位中，增加或部分更新一筆新的資料。
	DELETE：指定資料刪除。 （idempotent）
	```
*	Template Language(jade、slim、ejs)
*	boilerplate : 乾淨的開發環境
*	emmet : 一套面向文字編輯器的外掛程式，它允許通過內容輔助高速度的編寫和編輯HTML、XML、XSL和其他結構化的程式碼格式。
	```
	.warp>.menu>ul>li*6>a{hello}
	```
*	 snippet : 程式碼片段
*	WTForms : 一個非常好用而且強大的表單校驗和渲染的庫
*	(Google Tag Manager, GTM）: Google 代碼管理工具
* javascrip application
	```
	electronjs：寫一個跨平台的桌面應用程式
	Node.js：跨足後端，或倚賴核心開發各種應用程式
	React Native：設計雙平台 APP
	pixijs：透過 WebGL 開發動畫核心，跨足 3D 世界
	A-Frame：將 3D 介面以 VR 模式進行運作
	```
*	WEB Guideline : 
	```
	什麼色碼、尺寸、字體字級、間距…這都還可以算是 VI 的範圍
	它能確保不管是誰接手都能有相同的產出，而不至於換個人處理就換了個長相。
	也可以把它當成系統規格書、屬於文件的一種，條列式分章節，明確告訴你什麼可以做、什麼不能做、某種特定情況下該怎麼處理。
	```
*	COMPASS、Fire.app
*	CSS預處理器(css preprocessor)
*	susy
* compass : Sass 擴充套件
* grid system
* 960grid 
*	CSS Sprite - 張圖片合併
*	CMS(Content Management System) 內容管理系統
* web-font 雲端字型
* LAMP: Linux + Apache + MySql + PHP
* WAMP: Windows + Apache + MySql + PHP
*	XAMPP: XAMPP是一套幫你把LAMP或WAMP環境整合好的安裝程式
	[XAMPP](https://www.apachefriends.org/zh_tw/index.html)
### side project
*	學會新技術，拿舊專案重寫優化
*	臨時需要設計一個平台協助他人時，例如八仙塵爆，那時我也設計一個查詢介面，順便練習從 jQ 轉 NG 。
*	從 OPEN DATA 獲得寶貴數據資料，拿 JSON API 自行介接地圖、圖表資訊
*	思考大眾常遇到的問題，設計一個小服務來解決，當初的求職天演通其實也是從 side project 變成公司創業方向
*	從自己生活周遭不便來想靈感，例如寫一個 Node.js 爬蟲去抓最便宜的機票，若有釋出則發 Mail 通知
*	跟朋友組隊參加技術黑客松，將想練的技術在比賽過程中來發揮得淋漓盡致
*	做自己想做的服務，讓自己具有產品思維來運營它，未來的有一天說不定有機會靠它創業

### some target
*	增加 localstorage 功能，讓代辦事項紀錄起來，打開瀏覽器也看得到  
*	研究 Firebase database 資料庫功能，用 JS 去設計資料庫邏輯  
*	瞭解 FB API 邏輯，整合 Firebase Auth 功能，設計一個能夠讓綁定會員的 todolist 服務  
*	將程式上傳到 heroku 主機  
*	將程式整到 Electron，設計 Win、Mac 雙平台 APP  
*	介接第三方金流，讓服務能夠進行收款  
*	瞭解 chrome 插件設計邏輯，並讓 插件服務與網頁版能同時整合  
*	成長駭客 (Growth Hacking)
*	區塊鏈
*	WebGL 建置 3D 環境
*	React Native 建置雙平台 APP
*	AR、VR
*	PWA
*	AMP
* 電子商務網站
*	B2B 系統
* 網頁爬蟲
* 瀏覽器的渲染原理
*	Google的SpeedTracer
WordPress : 是一個以PHP和MySQL為平台的自由開源的部落格軟體和內容管理系統

### some information
*	謎戀貓
* 如何報價
	```
	有很多廠商都很習慣用「頁數」來訂價，例如一頁五百，十頁五千的算法，如果你真的用這樣來報，肯定會吃大虧
	主動提出來瀏覽器規格 : 如果網頁需要支援舊版 IE 時，報價我會提高到1.5~2倍
	螢幕解析度部分是否哪幾個版型會需要客製化(響應式網頁)
	以功能性來報價
		第一個網站的每個頁面都大致雷同，我將 Layout 開發好後，其它頁面只有中間的文字與圖片進行替換
		第二個網站每個頁面都需要客製化動畫效果，有些甚至必須得用 JS+CSS 輔助才有辦法呈現，而且還必須考慮熱門解析度上呈現也必須ok，而且需要不時地溝通網站細節，確保動態效果符合期待。而且部分頁面還必須接後端 API 。
		我剛成為前端沒多久，一個前端頁面我收一千，過幾年後我開始報一頁一萬，為什麼可以差到那麼多呢？一方面是我的能力提升，所以接的案子的頁面複雜度也比較高，另一方面是我認為自己有值這個價值
	依照工作天來推算
		假設一天的工作天價值3000元，同時要記住這個工作天是你休息進修時間抽出來再額外做的，所以價值高一些也 ok
	```
*	金錢、成就、技術能量
*	w3c 出了任何的草案、ECMAScript 出了哪些規範時，瀏覽器也會適版本號依序地納入新語法

### name 
banner/hero : 橫幅(版頭)

slide
introduce


### book
*	JavaScript & JQuery : 網站互動設計程式進化之道 


### flow
*	url 
	```
	get API : https://www.thef2e.com/api/signUpTotal

	```


### 後端語言
*	Node.js
*	PHP + MySQL
*	RUBY
*	NET + MSSQL

### 前端思考
*	瀏覽器原理：你知道瀏覽器的網頁渲染機制嗎？
*	資訊安全：你知道前端要如何寫才能避免 XSS 攻擊？
*	效能優化：當資料量多到無法負荷時，你該如何優化效能呢？
*	程式趨勢：你是否有掌握到目前最新趨勢的寫法，是否有目前雖然是測試階段，但你能預測到他未來有機會成為一個產品服務？
*	網站追蹤：你知道 SEO 嗎？有辦法與行銷部門協作，共同開發 Growth Hack 精神的 Funnel 追蹤呢？
*	WebGL 動態設計：你知道網頁甚至能夠在瀏覽器呈現 3D 介面，要你設計一個互動性線上遊戲你思考得環節夠全面嗎？
*	狀態設計：當網站離線狀態時，你的網站仍然有辦法運作，直到連線又能夠連接到伺服器去嗎？
*	協同開發：你有辦法和其它前端討論模組化概念，讓多位前端加倍開發產能在同一個專案上嗎？
*	無障礙設計：你有想過你的網站是否能讓身障人士都能輕鬆地瀏覽網頁嗎？
*	後端邏輯：你知道後端是如何傳送網頁資訊到瀏覽器的呢？知道什麼是 Header、狀態碼、Session、Cookie 嗎？


### chrome plug
*	Life Is Too Short  
*	Postman - 測試 API 的好工具
	```
		POST : https://www.thef2e.com/api/isSignUp
		Params-Headers 
			Key : Content-Type
			Value : application/json
		Params-Body-raw
		  {
	    	"email": "kyp001@yahoo.com.tw"
	  	}
	```

### record
	1. BEM(Block Element Modifier) : 一種 CSS class 命名的設計模式，將介面切割成許多獨立的區塊，以區塊（Block）、元素（Element）和修飾子（Modifier）來命名
		__ 區塊
		_ 狀態
	2. prefix 前綴
		l - layout
		e - element (h1, p, ul, button)
		p - page
		h - helper
		col- grid
		fas、fa - icon
		m - module (card, pagegrad)
	3. 斷點
			pc >= 1024
			pad 768~1023
			small pad 569~767
			mobil 320~568
	4. 書 - 使用者介面
	5. 文字
		//font
		$font-title: Helvetica Neue, Regular
		$font-Neue: Helvetica Neue, Regular
		$font-times: Times, Regular
	6. flexbox
	7. bs4-utility
	8. airbnb(JavaScript Style Guide)







