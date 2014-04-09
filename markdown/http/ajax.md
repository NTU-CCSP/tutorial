一般網頁
-------

![Round-trip websites](images/http/round-trip.png?borderless)

每次都要刷新整個畫面

---

著名的例子：Gmail
---

![gmail](images/http/gmail.png)

---

XMLHttpRequest
-------------
* DOM 提供之 API 之一
* 用 javascript 送 HTTP request 到 server
* 用 javascript 處理 server 回傳之資料
* 不用刷新整個頁面

---

AJAX
-------

### Asynchronous JavaScript and XML

<ul>
  <li class="fragment">用 XMLHttpRequest 和 server 溝通</li>
  <li class="fragment">曾使用當時最尖端的 XML 格式交換資料</li>
  <li class="fragment">用 Javascript 操作 DOM，執行動態效果</li>
  <li class="fragment">不等遠端回應，繼續執行（asynchronous）</li>
  <li class="fragment">用 callback 處理遠端回傳的資料</li>
</ul>

---

Callback
---

<ul>
  <li class="fragment">當事件發生、條件滿足的時候，才去執行的工作</li>
  <li class="fragment">去跟遠端溝通的時候，需要一段時間</li>
  <li class="fragment">但是程式不等人，<strike>立法與審查同時並行</strike></li>
  <li class="fragment">設置 Callback Function 來處理回應的資料</li>
</ul>


---

jQuery Ajax
-------------

jQuery 包裝了 Ajax 相關功能

* `$.get` 送 get request 給 server
* `$.post` 送 post request 給 server
* `$.ajax` 為 `$.get`、`$.post` 等 ajax 相關的核心 function

- - -

[jQuery Ajax 分類](http://api.jquery.com/category/ajax/)

---

`$.get` 範例
-------------

```
$.get(URL, DATA, CALLBACK, TYPE)
```

* `DATA`: 要送到遠端的資料，object 或字串。
* `TYPE`: 如何解讀遠端的回應，可以是 `'json'`, `'text'`, `'html'` 等。

[[yugak]]

---

Facebook
---
- 範例偷渡了跟臉書拿資料的方法
- 我們回過頭來逐條審查一下


---

Graph API Explorer
-------------------

[Graph API Explorer](https://developers.facebook.com/tools/explorer)

- - -

試試 `454607821247176` 可以拿得到什麼資源與欄位。

- - -

Page 物件有[很多 edge](https://developers.facebook.com/docs/graph-api/reference/page#edges)。

`454607821247176/posts` -- 塗鴉牆文章

`454607821247176/feed` -- 「Recent Posts by Others」

---

Token
-----

![令牌](images/http/token.jpg)

### 令牌

> 令牌是我國古代軍事所用的一種物品......通常由軍隊的最高長官發出，交給下屬軍官，用於在執行任務時，證明已經或了最高長官的指令或授權......類似於今天的介紹信、授權證明書或執法證件。
<a href="http://baike.baidu.com/view/544102.htm">-- 百度百科</a>

<div class="fragment">
  <hr>

  已獲授權的證明。
</div>

---

Access Token
------------

![進階授權畫面](images/http/extended.png)

裡頭有 App、目前的 Facebook 使用者是誰、允許的權限項目、登入時間等資訊（所以會 expire）。

[Login Permissions Reference](https://developers.facebook.com/docs/reference/login/#permissions)

Graph API 裡的 field 與 connection 都有[相對應的權限](https://developers.facebook.com/docs/graph-api/reference/page)。

---


`$.getJSON`
-------------

```
$.getJSON(URL, DATA, CALLBACK)
```

`$.get(URL, DATA, CALLBACK, 'json')` 的簡寫。

[[mrorz-ajax-demo2]]

---


Send data to Facebook API
---

[[get-facebook-friend]]

---

取得朋友的照片
---
[[get-friend-album]]
<p class="fragment">那如果要取得自己所有的朋友照片呢？</p>
<p class="fragment">Callback and Callback again!</p>
<p class="fragment">SO WE NEED PROMISE</p>

---

CORS
-------------

### Cross-Origin Resource Sharing

```
Origin http://localhost:3000 is not allowed by Access-Control-Allow-Origin.
```

<hr>

<p class="fragment">
瀏覽器不會信任來自別的網域的 ajax response。
</p>

<p class="fragment">
除非 response 裡有 `Access-Control-Allow-Origin` 這個 header。
</p>

<p class="fragment">
javascript 向當前頁面的 domain 送 ajax，則沒有這個問題。
</p>
