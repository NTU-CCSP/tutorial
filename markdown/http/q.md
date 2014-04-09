Scenario
---------

<p class="fragment">正妹/型男好友牆</p>
<p class="fragment">秀出你所有的異性/同性好友</p>
<p class="fragment">每個人的大頭貼顯示為最高讚數的一張。</p>

---



Graph API / FQL
---------

[Graph API Reference](https://developers.facebook.com/docs/reference/api/)

能讀取或發佈各種資源；每項資源裡有 fields（欄位）和 edges（巢狀資源）。

- - -

[FQL](https://developers.facebook.com/docs/reference/fql/)

將 Graph API 裡的「物件」當成資料庫的「資料表」來操作，可以拿到比較多資源、下比較複雜的指令。

---



Divide into Subtasks
---------

<ul>
  <li class="fragment">(ajax) 拿到一個人的所有朋友（必須包含性別資訊）</li>
  <li class="fragment">過濾我們想要的性別</li>
  <li class="fragment">(ajax) 拿每個朋友的相簿列表</li>
  <li class="fragment">找出Profile Pictures</li>
  <li class="fragment">(ajax) 針對每個人的Profile Pictures</li>
  <li class="fragment">找出最高讚數的相片</li>
</ul>

---



Get Friends
---------

* [jQuery $.getJSON](https://api.jquery.com/jQuery.getJSON/)
* [Facebook /{user-id}/friends](https://developers.facebook.com/docs/graph-api/reference/user/friends/)

[[get-friends]]

---



Get Friends Albums
---------

* [Facebook /{user-id}/albums](https://developers.facebook.com/docs/graph-api/reference/user/albums/)

[[get-friends-albums]]

---



Get Album Photos
---------

* [Facebook /{user-id}/albums](https://developers.facebook.com/docs/graph-api/reference/user/albums/)

[[get-album-photos]]

---



Put Everything Together
---------

* [Array::forEach](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
* [Array::filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
* [Array::sort](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)

[[get-friends-famous-photo]]

---



Get Friends
---------

* [kriskowal/q](https://github.com/kriskowal/q)
* [Q(value)](https://github.com/kriskowal/q/wiki/API-Reference#qvalue)
* [jQuery to Q](https://github.com/kriskowal/q/wiki/Coming-from-jQuery#converting-jquery-promises-to-q)

[[with-q-get-friends]]

---



Get Friends Albums
---------

[[with-q-get-friend-albums]]

---



Get Album Photos
---------

[[with-q-get-album-photos]]

---



Put Everything Together
---------

* [Q.all](https://github.com/kriskowal/q/wiki/API-Reference#promiseall)

[[with-q-get-friends-famous-photo]]
