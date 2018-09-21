# Node.js issue

*   [Root](../README.md)
*   [1. Unsupported platform for fsevents@1.2.4: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"}](#a1)

<h2 id="a1">1. Unsupported platform for fsevents@1.2.4: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"}</h2>

```
npm WARN week2_filter_2nd@1.0.0 No repository field.
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.4 (node_modules\fsevents):
npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@
1.2.4: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"})
```

**fsevent是mac osx系統的東西，在win或者Linux下使用了會有警告，忽略即可。意思就是你已經安裝成功了...**






