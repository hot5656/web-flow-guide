# JavaScript issue

*   [Root](../README.md)
*   [1. ajax - No 'Access-Control-Allow-Origin' header is present on the requested resource](#a1)
*   [2. ajax post JSON format issue for chrome](#a2)

<h2 id="a1">1. ajax - No 'Access-Control-Allow-Origin' header is present on the requested resource</h2>

>	瀏覽器因為安全性的考量，有一個東西叫做同源政策(Same-origin policy)
```
1. 有些網站設計成只擋http 不擋https
2. Server 要設為 Access-Control-Allow-Origin: *
    CORS(Cross-Origin Resource Sharing)
3. browser disabel "Same-origin policy"
```

<h2 id="a2">2. ajax post JSON format issue for chrome</h2>
```
Ajax 在 chrome 執行,設定為 ajaxHandler.setRequestHeader('Content-type', "application/json")
送出 ajax command 第一次 Content-type 會有問題,會自動送第二次就正常 
```


