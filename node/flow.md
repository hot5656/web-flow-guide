# Node.js flow

*   [Root](../README.md)
*   [1. SASS compile](#a1)
*   [2. npm command](#a2)
*   [3. mini-web server](#a3)

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

```

<h2 id="a3">3. mini-web server</h2>

```
// start mini-web server
node_modules\.bin\browser-sync start --server --files="index.html, *.js, stylesheets\*.css"

// script 
"start" : "./node_modules/.bin/browser-sync start --server --no-notify --files=`index.html, *.js, stylesheets/*.css`",

預設的網址 http://localhost:3000
UI網址     http://localhost:3001 (沒多大作用)

--files     : 參數宣告Browser-Sync要去監聽那些檔案的異動,當那些檔案變動時,則執行瀏覽器頁面刷新的動作
--no-notify : no notify web link

```


	
