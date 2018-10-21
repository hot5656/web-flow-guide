# Node.js record

*   [Root](../README.md)
*   [1. SASS compile](#a1)
*   [2. npm command](#a2)
*   [3. mini-web server](#a3)
*   [4. 解釋名詞](#a4)
*   [5. Ajax](#a5)
*   [6. package](#a6)
*   [7. generate package.json](#a7)
*   [8. gulp](#a8)
*   [9. nvm-node.js 管理程式](#a9)

<h2 id="a1">1. SASS compile</h2>

### normal compile

`node-sass --output-style expanded --source-map true --source-map-contents true --precision 6 scss\bootsrap\4.1.3\ -o stylesheets\bootsrap\4.1.3\`

### compile add debug
`node-sass --source-comments --output-style expanded --source-map true --source-map-contents true --precision 6 scss\bootsrap\4.1.3\ -o stylesheets\bootsrap\4.1.3\`
### compile add watch
`node-sass -w --output-style expanded --source-map true --source-map-contents true --precision 6 scss\bootsrap\4.1.3\ -o stylesheets\bootsrap\4.1.3\`

<h2 id="a2">2. npm command</h2>

```
// install to global  
npm install node-sass -g

// run script
npm run css-compile-sw

// npm install to local
npm install

// install develop package and save to package.json file
npm install  browser-sync -save-dev

// install package and save to package.json file
npm install  browser-sync -save

// list all package
npm ls -g
npm ls

// install pacjage latest version
npm i fsevents@latest -save-dev

// install yarn (seem snot usefull)
npm install yarn -g

// update npm package
// windows have some issuse for portable version, seem install version ok
npm i npm -g

// show package lastest version
npm info browser-sync version
or
npm view browser-sync version

// show package install version
npm list --depth 1 -g npm
node -v

// npm install to local(reference package.json file)
npm install

// uptate all package
npm update

// uptate one package
npm update <package>

// generate package.json
npm init

// package.json script add  comments
"scripts": {
    "//x": "build css for bootstrap",
    "start": "./node_modules/.bin/browser-sync start --server --no-notify --files=`index.html, *.js, stylesheets/*.css`"
},
```

<h2 id="a3">3. mini-web server</h2>

```
// need module 
browser-sync

// install develop package and save to package.json file
npm install  browser-sync -save-dev

// start mini-web server
node_modules\.bin\browser-sync start --server --files="index.html, *.js, stylesheets\*.css"

// script 
"start" : "./node_modules/.bin/browser-sync start --server --no-notify --files=`index.html, *.js, stylesheets/*.css`"

預設的網址 http://localhost:3000
UI網址     http://localhost:3001 (沒多大作用)

--files     : 參數宣告Browser-Sync要去監聽那些檔案的異動,當那些檔案變動時,則執行瀏覽器頁面刷新的動作
--no-notify : no notify web link
```

<h2 id="a4">4. 解釋名詞</h2>

```
NVM : 多版本控制
```


<h2 id="a5">5. Ajax</h2>
	
```javascript
// ajax site and id
var kcgSearchSite = "https://data.kcg.gov.tw/api/action/datastore_search";
var kcgTripId = "92290ee5-6e61-456f-80c0-249eae2fcc97";
// prepare save data
var tripList = [] ;
// wait for complete
var run = true ;
// ajax data object
var data = {
    resource_id: kcgTripId,
    offset: 0
};

$(document).ready(function() {
	// get trip data
	data.offset = 0 ;
	while(true) {
		getTripDat(data, tripList);
		data.offset += 100 ;
		if (!run) {
			break;
		}
	}

	// show trip data
	console.log(tripList);
});

function getTripDat(data, tripList) {
	var next ;

	$.ajax({
		url: kcgSearchSite,
		data: data,
		datatype:"json",
		async: false, // set sync (default async)
		error: function (xhr, ajaxOptions, thrownError) {
			// console.log(xhr);
			run = false ;
		},
		success:  function (respData, textStatus) {
			next = respData.result._links.next;

			if (respData.result.records.length > 0 ) {
				for(var j=0 ; j<respData.result.records.length ; j++) {
					tripList.push(respData.result.records[j]);
				}
			}
			else {
				run = false ;
			}
		},
	});
}

```

<h2 id="a6">6. package</h2>

```
// browser-sync
啟動 BrowserSync 的服務時，監看我們任何網頁的 html 或 css 檔案做異動的時候，自動重新讀取頁面


```


<h2 id="a7">7. generate package.json</h2>

```
npm init
```


<h2 id="a8">8. gulp</h2>

```
// install gulp to globak
npm install gulp -g

// install 
npm install
```

<h2 id="a9">9. nvm-node.js 管理程式</h2>

```
nvm -v  // version
nvm list avrible // avarible node.js
nvm install 8.11.2 // intall node.js 8.11.2
nvm list // list all install node.js
nvm use 8.11.2 // switch to node.js 8.11.2
```