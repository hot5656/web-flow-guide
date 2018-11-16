# Sass issue

*   [Root](../README.md)
*   [1. compass Inconsistent indentation: 1 tab was used for indentation, but the rest of the document was indented using 2 spaces](#a1)
*   [2. sass/scss 中文輸入問題 Invalid CP950 character "\xE6"](#a2)
*   [3. File to import not found or unreadable: mixin		// 放置所有Sass全域變數與Mixin."](#a3)
*   [4. sass Error: Invalid CSS after "...x solid #000; }": expected 1 selector or at-rule, was "{"](#a4)
*   [5. sass Error: Undefined variable: "$c-primary", but generate .css](#a5)


<h2 id="a1">1. compass Inconsistent indentation: 1 tab was used for indentation, but the rest of the document was indented using 2 spaces</h2>

```
File conevr indentation to space 
```

<h2 id="a2">2. sass/scss 中文輸入問題 Invalid CP950 character "\xE6"</h2>

```
	// file -- config.rb
	Encoding.default_external = 'utf-8'
```

<h2 id="a3">3. File to import not found or unreadable: mixin		// 放置所有Sass全域變數與Mixin.</h2>

```
import 後面不可以放 comment
@import mixin		// 放置所有Sass全域變數與Mixin
	-->
// 放置所有Sass全域變數與Mixin	
@import mixin
```


<h2 id="a4">4. sass Error: Invalid CSS after "...x solid #000; }": expected 1 selector or at-rule, was "{"</h2>
```
1. 使用空格進行縮排
2. 將縮排轉換成空格
```

<h2 id="a5">5. sass Error: Undefined variable: "$c-primary", but generate .css</h2>

```javascript
[16:28:47] Starting 'copy'...
[16:28:47] Finished 'copy' after 969 μs
[16:28:47] Starting 'sass'...
Error in plugin "sass"
Message:
    source\sass\layout\l-footer.sass
Error: Undefined variable: "$c-primary".
        on line 13 of source/sass/layout/l-footer.sass
>>      background: $c-primary;

   -------------^

[Browsersync] 2 files changed (all.css.map, all.css)
[16:28:47] Finished 'sass' after 271 ms
[Browsersync] Reloading Browsers... (buffered 18 events)

--> in the .sass add import as below 
@import ../init/variable
```


