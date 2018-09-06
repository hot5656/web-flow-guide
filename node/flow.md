# Node.js flow

*   [Root](../README.md)
*   [1. SASS compile](#a1)
*   [2. normal flow](#a2)

<h2 id="a1">1. SASS compile</h2>

### normal compile

`node-sass --output-style expanded --source-map true --source-map-contents true --precision 6 scss\bootsrap\4.1.3\ -o stylesheets\bootsrap\4.1.3\`

### compile add debug
`node-sass --source-comments --output-style expanded --source-map true --source-map-contents true --precision 6 scss\bootsrap\4.1.3\ -o stylesheets\bootsrap\4.1.3\`
### compile add watch
`node-sass -w --output-style expanded --source-map true --source-map-contents true --precision 6 scss\bootsrap\4.1.3\ -o stylesheets\bootsrap\4.1.3\`

<h2 id="a2">2. normal flow</h2>

### install to global  
```
npm install node-sass -g
```
### run script
```
npm run css-compile-sw
```



	
