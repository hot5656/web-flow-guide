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

// show gulp-util global version
npm ls gulp-util -g
// show gulp-util local version
npm ls gulp-util

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

// install npm-check-updates
npm install npm-check-updates
// Show any new dependencies for the project in the current directory
node_modules\.bin\ncu
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
// browser-sync - Live CSS Reload & Browser Syncin
啟動 BrowserSync 的服務時，監看我們任何網頁的 html 或 css 檔案做異動的時候，自動重新讀取頁面
// ejs : Embedded JavaScript templates
// minimist : parse argument options

// gulp plugin
gulp-plumber : 錯誤處理(提示) - Prevent pipe breaking caused by errors from gulp plugins
gulp-load-plugins : 自動加載 gulp plugin from package.json
gulp-sourcemaps : 用來生成sourcemap 文件。用於當less 或sass 文件中有各種引入關係
gulp-sass : 編譯 sass/scss 檔案
	// Sass 編譯的風格總共有四種：
	nested (預設的樣式) : 巢狀顯示
	expanded : 不要巢狀
	compact : 簡潔樣式，縮進成一行
	compressed ：壓縮模式
gulp-postcss : plugin to pipe CSS through several plugins, but parse CSS only once.
autoprefixer : add prefix for scss
gulp-concat：合併檔案
gulp-uglify：混淆並壓縮 JS(Minify JavaScript with UglifyJS3.)
gulp-rename：重新命名檔案
gulp-front-matter : 模板設置 frontMatter
gulp-clean : gulp-clean
gulpSequence : Run a series of gulp tasks in order
gulp-sequence : Run a series of gulp tasks in order.
gulp-gh-pages : publish contents to Github pages
gulp-if : conditionally control the flow of vinyl objects.
gulp-clean-css(instead gulp-minify-css) :  壓縮 CSS, using clean-css
gulp-uglify : JSHint plugin for gulp
gulp-babel : Use next generation JavaScript, today, with Babel
gulp-layout : Gulp plugin to switch layout files for each content

// js use
eslint : ESLint is a tool for identifying and reporting on patterns found in ECMAScript/JavaScript code. In many ways, it is similar to JSLint and JSHint with a few exceptions:
eslint-config-airbnb-base : This package provides Airbnb's base JS .eslintrc (without React plugins) as an extensible shared config.
eslint-plugin-import : This plugin intends to support linting of ES2015+ (ES6+) import/export syntax, and prevent issues with misspelling of file paths and import names.
browserify(instead gulp-browserify) : Use a node-style require() to organize your browser code and load modules installed by npm.
lodash : The Lodash library exported as Node.js modules.
// package
bootstrap : 
jquery : 
```

<h2 id="a7">7. generate package.json</h2>

```
npm init
```


<h2 id="a8">8. gulp</h2>

*	a example  

```javascript
// install gulp to global
npm install gulp -g

// generate package.json
npm init

// install susy - if need
npm install susy --save-dev

// install gulp for develp at local
npm install gulp --save-dev
npm install browser-sync --save-dev
npm install gulp-load-plugins --save-dev
npm install autoprefixer --save-dev
npm install gulp-plumber --save-dev
npm install gulp-sourcemaps --save-dev
npm install gulp-sass --save-dev
npm install gulp-postcss --save-dev
npm install gulp-if --save-dev
npm install gulp-clean-css --save-dev
npm install minimist --save-dev
npm install gulp-clean --save-dev

// layout using ejs format
npm install gulp-front-matter --save-dev
npm install gulp-layout --save-dev
npm install ejs --save-dev


// add file gulpfile.js
// variabel 
const gulp = require('gulp');
const $ = require('gulp-load-plugins')();
const browserSync = require('browser-sync');
const autoprefixer = require('autoprefixer');
const minimist = require('minimist'); // 用來讀取指令轉成變數

// env process
// production || development
// # gulp --env production
const envOptions = {
  string: 'env',
  default: { env: 'development' },
};

var options = minimist(process.argv.slice(2), envOptions);
console.log(options);
// --- env process

// load browser-sync
gulp.task('browserSync', () => {
  browserSync.init({
    server: { baseDir: './public' },
    reloadDebounce: 2000,
  });
});

// copy file to public (not include sass,ejs and html  )
gulp.task('copy', () => {
  gulp
    .src(['./source/**/**', '!source/sass/**/**', '!source/**/*.ejs', '!source/**/*.html'])
    .pipe(gulp.dest('./public/'))
    .pipe(
      browserSync.reload({
        stream: true,
      }),
    );
});

// sass process
gulp.task('sass', () => {
  // PostCSS AutoPrefixer
  const processors = [
    autoprefixer({
      browsers: ['last 5 version'],
    }),
  ];

  return gulp
    .src(['./source/sass/**/*.sass', './source/sass/**/*.scss'])
    .pipe($.plumber())
    .pipe($.sourcemaps.init())
    .pipe(
      $.sass({
        outputStyle: 'nested',
        includePaths: ['./node_modules/susy/sass'],		// addition include sass
      }).on('error', $.sass.logError),
    )
    .pipe($.postcss(processors))
    .pipe($.if(options.env === 'production', $.cleanCss())) // 假設開發環境則壓縮 CSS
    .pipe($.sourcemaps.write('.'))
    .pipe(gulp.dest('./public/css'))
    .pipe(
      browserSync.reload({
        stream: true,
      }),
    );
});

// clear pubic file 
gulp.task('clean', () => {
  return gulp.src(['./public'], { read: false }).pipe($.clean());
});

// layout process
gulp.task('layout', () => {
  return gulp
    .src(['./source/**/*.html'])
    .pipe($.plumber())
    .pipe($.frontMatter())  // 模板設置
    .pipe(
      $.layout((file) => {  // ejs 模板設置
        return file.frontMatter;
      }),
    )
    .pipe(gulp.dest('./public'))
    .pipe(
      browserSync.reload({
        stream: true,
      }),
    );
});

// watch process
gulp.task('watch', () => {
  gulp.watch(['./source/sass/**/*.sass', './source/sass/**/*.scss'], ['sass']);
  gulp.watch(['./source/**/**', '!source/sass/**/**', '!source/**/*.ejs', 'source/**/*.html'], ['copy']);
  gulp.watch(['./source/**/*.ejs', './source/**/*.html'], ['layout']);
});

// default task
gulp.task('default', ['copy', 'sass', 'layout', 'browserSync', 'watch']);
gulp.task('default', ['copy', 'sass', 'vendorJs', 'browserSync', 'layout', 'watch']);

// layout.ejs example
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<meta http-equiv="X-UA-Compatible" content="ie=edge">
	<title>Document <%- title %></title>
	<link rel="stylesheet" href="css/all.css">
</head>
<body>
	<% if (current === 'index') { %>
		<h1>INDEX</h1>
	<%} %>
	// html content
	<%- contents %>
	// html content end
</body>
</html>

// html example 
---
title: 首頁
layout: ./source/layout.ejs
engine: ejs
current: index
---

<section>
	<nav>
		nav: span 2
	</nav>

	<main>
		main: span 6
	</main>

	<footer>
		footer: span all
	</footer>
</section>	

```

*	flow register 

``` javascript
// install gulp to global
npm install gulp -g

// generate package.json
npm init

// install gulp for develp at local
npm install gulp --save-dev

// 加載
	// 載入 gulp
	var gulp = require('gulp');
	// 載入 gulp-load-plugins
	const $ = require('gulp-load-plugins')();
	// 載入 browser-sync
	const browserSync = require('browser-sync');
	// 載入 autoprefixer
	const autoprefixer = require('autoprefixer');
	// 載入 minimist - parse argument options
	const minimist = require('minimist'); // 用來讀取指令轉成變數
	// 載入 gulp-sequence
	const gulpSequence = require('gulp-sequence');

// add gulpfile.js - gulp flow
	//定義一個任務名稱，來指定任務的工作內容
	gulp.task(name, fn)
	// 指定檔案來源
	gulp.src(glob)
	// 檔案的存檔位置
	gulp.dest(folder)
	// 關注特定檔案是否更動
	gulp.watch(glob, cb)
	// 運行指定的任務
	gulp.run(task) 

// add gulpfile.js - example
	// parse argument example 
	// # gulp sass --env production
	// # gulp --env production
	const minimist = require('minimist'); 
	const envOptions = {
	  string: 'env',
	  default: { env: 'development' },
	};
	var options = minimist(process.argv.slice(2), envOptions);
	console.log(options);
	.pipe($.if(options.env === 'production', $.cleanCss())) // 假設開發環境則壓縮 CSS

	// default task run 哪幾個 task
	gulp.task('default', ['copy', 'sass', 'vendorJs', 'browserSync', 'layout', 'watch']);
	
	// gulp-sequence example
	gulp.task('sequence', gulpSequence('clean', 'copy', 'sass', 'vendorJs', 'layout', 'sass'));

	// copy file : 包含那些檔案 --> load to --> copy 
	gulp.task('copy', () => {
	  gulp
	    .src(['./source/**/**', '!source/stylesheets/**/**', '!source/**/*.ejs', '!source/**/*.html'])
	    .pipe(gulp.dest('./public/'))
	    .pipe(
	      browserSync.reload({
	        stream: true,
	      }),
	    );
	});

	// sass process --> plumber --> init sourcemap for sass --> add fprefix
	gulp.task('sass', () => {
	  // PostCSS AutoPrefixer
	  const processors = [
	    autoprefixer({
	      browsers: ['last 5 version'],
	    }),
	  ];

	  return gulp
	    .src(['./source/stylesheets/**/*.sass', './source/stylesheets/**/*.scss'])
	    .pipe($.plumber())
	    .pipe($.sourcemaps.init())
	    .pipe(
	      $.sass({
	        outputStyle: 'nested',
	        includePaths: ['./node_modules/bootstrap/scss'],
	      }).on('error', $.sass.logError),
	    )
	    .pipe($.postcss(processors))
	    .pipe($.if(options.env === 'production', $.cleanCss())) // 假設開發環境則壓縮 CSS
	    .pipe($.sourcemaps.write('.'))
	    .pipe(gulp.dest('./public/stylesheets'))
	    .pipe(
	      browserSync.reload({
	        stream: true,
	      }),
	    );
	});

	// merge vender JS
	gulp.task('vendorJs', () => {
	  return gulp
	    .src([
	      './node_modules/jquery/dist/jquery.slim.min.js',
	      './node_modules/bootstrap/dist/js/bootstrap.bundle.min.js',
	    ])
	    .pipe($.concat('vendor.js'))
	    .pipe(gulp.dest('./public/javascripts'));
	});

	// run browser sync - debounce 2s
	gulp.task('browserSync', () => {
	  browserSync.init({
	    server: { baseDir: './public' },
	    reloadDebounce: 2000,
	  });
	});	

	// layout 
	gulp.task('layout', () => {
	  return gulp
	    .src(['./source/**/*.ejs', './source/**/*.html'])
	    .pipe($.plumber())
	    .pipe($.frontMatter())
	    .pipe(
	      $.layout((file) => {
	        return file.frontMatter;
	      }),
	    )
	    .pipe(gulp.dest('./public'))
	    .pipe(
	      browserSync.reload({
	        stream: true,
	      }),
	    );
	});	

	// run browseSync
	gulp.task('browserSync', () => {
	  browserSync.init({
	    server: { baseDir: './public' },
	    reloadDebounce: 2000,
	  });
	});

	// watch 
	gulp.task('watch', () => {
	  gulp.watch(['./source/stylesheets/**/*.sass', './source/stylesheets/**/*.scss'], ['sass']);
	  gulp.watch(['./source/**/**', '!/source/stylesheets/**/**'], ['copy']);
	  gulp.watch(['./source/**/*.ejs', './source/**/*.html'], ['layout']);
	});

	// deploy to gihub
	gulp.task('deploy', () => {
	  return gulp.src('./public/**/*').pipe($.ghPages());
	});

	// 檢查JavaScript代碼錯誤
	gulp.task('scripts',function(){
	    gulp.src('./js/*/js')
	    .pipe(concat('all.js'))
	    .pipe(gulp.dest('./dist'))
	    .pipe(rename('all.min.js'))
	    .pipe(uglify())
	    .pipe(gulp.dest('./dist'));
	});
```

<h2 id="a9">9. nvm-node.js 管理程式</h2>

```
nvm -v  // version
nvm list avrible // avarible node.js
nvm install 8.11.2 // intall node.js 8.11.2
nvm list // list all install node.js
nvm use 8.11.2 // switch to node.js 8.11.2
```

