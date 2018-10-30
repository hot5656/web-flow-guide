# Node.js issue

*   [Root](../README.md)
*   [1. Unsupported platform for fsevents@1.2.4: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"}](#a1)
*   [2. install browser-sync issue](#a2)
*   [3. run gulp -> Failed to load external module @babel/register](#a3)
*   [4. run gulp -> some WARN](#a4)
*   [5. Failed to load external module @babel/register](#a5)

<h2 id="a1">1. Unsupported platform for fsevents@1.2.4: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"}</h2>

```
npm WARN week2_filter_2nd@1.0.0 No repository field.
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.4 (node_modules\fsevents):
npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@
1.2.4: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"})
```

**fsevent是mac osx系統的東西，在win或者Linux下使用了會有警告，忽略即可。意思就是你已經安裝成功了...**


<h2 id="a2">2. install browser-sync issu</h2>

```
npm audit

                       === npm audit security report ===


                                 Manual Review
             Some vulnerabilities require your attention to resolve

          Visit https://go.npm.me/audit-guide for additional guidance


  Low             Regular Expression Denial of Service

  Package         debug

  Patched in      >= 2.6.9 < 3.0.0 || >= 3.1.0

  Dependency of   browser-sync [dev]

  Path            browser-sync > localtunnel > debug

  More info       https://nodesecurity.io/advisories/534

found 1 low severity vulnerability in 5248 scanned packages
  1 vulnerability requires manual review. See the full report for details.
```
**browser-sync僅為development使用,upgrade debug package 還是會發生故不處理**


<h2 id="a3">3. run gulp -> Failed to load external module @babel/register</h2>

```
solved it by downgrading the gulp version from 3.9.1 to 3.9.0. Looks like 3.9.1 is buggy.
```

<h2 id="a4">4. run gulp -> some WARN</h2>

```
* npm WARN deprecated gulp-util@3.0.8: gulp-util is deprecated - replace it,following the guidelines at https://medium.com/gulpjs/gulp-util-ca3b1f9f9ac5
* npm WARN deprecated graceful-fs@3.0.11: please upgrade to graceful-fs 4 for compatibility with current and future versions of Node.js
* npm WARN deprecated minimatch@2.0.10: Please update to minimatch 3.0.2 or higher to avoid a RegExp DoS issue
* npm WARN deprecated minimatch@0.2.14: Please update to minimatch 3.0.2 or higher to avoid a RegExp DoS issue
* npm WARN deprecated graceful-fs@1.2.3: please upgrade to graceful-fs 4 for compatibility with current and future versions of Node.js

WARN 1 : not use gulp-util and use below API
	gutil.File => https://www.npmjs.com/package/vinyl
	gutil.replaceExtension => The .extname property on Vinyl objects or https://www.npmjs.com/package/replace-ext
	gutil.colors => https://www.npmjs.com/package/ansi-colors
	gutil.date => https://www.npmjs.com/package/date-format
	gutil.log => https://www.npmjs.com/package/fancy-log
	gutil.template => https://www.npmjs.com/package/lodash.template
	gutil.env => https://www.npmjs.com/package/minimist
	gutil.beep => https://www.npmjs.com/package/beeper
	gutil.noop => https://www.npmjs.com/package/through2
	gutil.isStream => Use the .isStream() method on Vinyl objects
	gutil.isBuffer => Use the .isBuffer() method on Vinyl objects
	gutil.isNull => Use the .isNull() method on Vinyl objects
	gutil.linefeed => Use the string '\n' in your code
	gutil.combine => https://www.npmjs.com/package/multipipe
	gutil.buffer => https://www.npmjs.com/package/list-stream
	gutil.PluginError => https://www.npmjs.com/package/plugin-error
WARN 2~5 僅為提示且在其他module內,不處理
```

<h2 id="a5">5. Failed to load external module @babel/register</h2>

```
// [17:06:58] Failed to load external module @babel/register
// [17:06:58] Requiring external module babel-register
This is just a warning that Gulp failed to load @babel/register but on the next line it successfully loaded the fallback module: babel-register
https://github.com/gulpjs/gulp/issues/1631
You could install the babel-core/register module to remove the warning, but it's not necessary.
```