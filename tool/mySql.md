# MySQL

*   [Root](../README.md)
*   [1. Issue](#a1)
*   [2. Reference link](#a2)
*   [3. Basic](#a3)


<h2 id="a1">1. Issue</h2>


<h2 id="a2">2. Reference link</h2>


<h2 id="a3">3. Basic</h2>

*	tool

```
UwAMP (PHP using newest 7.1 or 7.2)
Laravel wagon
xAMPP
```

*	名詞
	*	正規畫 Normalization
	*	MySQL
	*	MongoDB
	*	SQL inject(讓輸入變成程式的一部分)

	```
	// 
	是在輸入的字串之中夾帶SQL指令，在設計不良的程式當中忽略了字元檢查，那麼這些夾帶進去的惡意指令就會被資料庫伺服器誤認為是正常的SQL指令而執行，因此遭到破壞或是入侵
	select * from users 
		where username='huli' and password='123'

	select * from users 
		where username='' or 1=1 --' and password=''
		--> 
			-- 表註解
			忽略--後所有東西
	```

