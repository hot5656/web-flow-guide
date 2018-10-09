# Node.js issue

*   [Root](../README.md)
*   [1. Unsupported platform for fsevents@1.2.4: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"}](#a1)
*   [2. install browser-sync issue](#a2)
*   [3. run gulp -> Failed to load external module @babel/register](#a3)

<h2 id="a1">1. Unsupported platform for fsevents@1.2.4: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"}</h2>

```
npm WARN week2_filter_2nd@1.0.0 No repository field.
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.4 (node_modules\fsevents):
npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@
1.2.4: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"})
```

**fsevent是mac osx系統的東西，在win或者Linux下使用了會有警告，忽略即可。意思就是你已經安裝成功了...**


<h2 id="a2">install browser-sync issue}</h2>

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


<h2 id="a3">3. run gulp -> Failed to load external module @babel/register}</h2>

```
solved it by downgrading the gulp version from 3.9.1 to 3.9.0. Looks like 3.9.1 is buggy.
```


