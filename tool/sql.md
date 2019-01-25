
*	SQL inject(讓輸入變成程式的一部分)

```
select * from users 
	where username='huli' and password='123'

select * from users 
	where username='' or 1=1 --' and password=''
	--> 
		-- 表註解
		忽略--後所有東西
```

* XSS(cross site scripting) - 讓輸入變成程式的一部分
過濾/解析 使用者符號
輸入 : <h1>Hi</h1> 

MySQL
MongoDB
Jest : https://jestjs.io/
npm install jest --save-dev 

 og tag : 利用 Facebook debugger 驗證是否成功 https://developers.facebook.com/tools/debug/