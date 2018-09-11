# JavaScript issue

*   [Root](../README.md)
*   [1. ajax - No 'Access-Control-Allow-Origin' header is present on the requested resource](#a1)

<h2 id="a1">1. ajax - No 'Access-Control-Allow-Origin' header is present on the requested resource</h2>

>	瀏覽器因為安全性的考量，有一個東西叫做同源政策(Same-origin policy)


```
1. 有些網站設計成只擋http 不擋https
2. Server 要設為 Access-Control-Allow-Origin: *
	CORS(Cross-Origin Resource Sharing)
3. browser disabel "Same-origin policy"
```




