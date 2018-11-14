# Sass issue

*   [Root](../README.md)
*   [1. compass Inconsistent indentation: 1 tab was used for indentation, but the rest of the document was indented using 2 spaces](#a1)
*   [2. sass/scss 中文輸入問題 Invalid CP950 character "\xE6"](#a2)
*   [3. File to import not found or unreadable: mixin		// 放置所有Sass全域變數與Mixin."](#a3)
*   [4. sass Error: Invalid CSS after "...x solid #000; }": expected 1 selector or at-rule, was "{"](#a4)


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

