`var` 敘述
---------

### 建立新的抽屜

----
<div class="row">
<div class="span3">
  <pre><code>
  var count;
  </code></pre>

  <p>建立名為 `count` 的空抽屜</p>
</div>
<div class="span3">
  <pre><code>
  var count = 0;
  </code></pre>

  <p>建立 `count` 並把 0 放進去</p>
</div>
</div>

----

`=` ：設定（Assign）。（不是「等於」喔！）

把「`=`」右邊的值（資料），放進等號左邊的變數（抽屜）。

<p class="fragment">等號的左邊一定要是一個變數。</p>

---

`=`： Assignment Operator
------------------------

<div class="row">
  <div class="span5">
    <pre><code>
    count = count + 1;
    </code></pre>

    遞增 `count` 值，放回 `count`抽屜中。
  </div>
  <div class="span1">
    <figure>
      <img src="images/programming/counter.jpg" alt="Counter" width="100">
      <figcaption>
        <small>
        [圖片來源](http://www.trigonalworld.com/2011_07_01_archive.html)
        </small>
      </figcaption>
    </figure>
  </div>
</div>

---

其他 Operator
------

* 負數 : `-` (如 `-35`)<br><small>執行結果：新數字</small>
* 算數 : `*` &nbsp; `/` &nbsp; `%` &nbsp; `+` &nbsp; `-`<br><small>執行結果：數字運算結果</small>
* 比大小 : `===`  &nbsp; `!==`  &nbsp; `<`  &nbsp; `>`  &nbsp; `<=` &nbsp;  `>=`<br><small>執行結果：`true` 或 `false`</small>

[[mrorz-js-operator?javascript,console]]

---

其他 Operator (2)
-------
* 邏輯運算 : `&&` &nbsp;  `||` &nbsp;  `!`<br><small>執行結果：`true` 或 `false`</small>
* 三元運算子 : `A ? B : C`<br><small>B、C 的執行結果擇一</small>
* 設定 : `=` &nbsp; `+=` &nbsp; `-=` &nbsp; `*=` &nbsp; `/=` &nbsp; `%=`<br><small>執行結果：等號左邊的變數值改變</small>

[[mrorz-js-operator2?javascript,console]]

---

「Operator `==`」很難用
----------

[[tedusiki?js,console]]

請使用沒有爭議的 `===`，或者是試著記熟 [`==` 型別轉換](http://javascriptweblog.wordpress.com/2011/02/07/truth-equality-and-javascript/)。


---

資料型態 (Data Type)
------------------

<div class="row">
  <div class="span1">
    <figure>
      <img src="images/programming/drawer-type.jpg" alt="Drawer labels" width="200">
      <figcaption><small>
        [圖片來源](http://inmyownstyle.com/2013/03/how-to-age-brass-in-less-than-5-minutes.html)
      </small></figcaption>
    </figure>
    
  </div>
  <div class="span5">
    <p>抽屜裡可以放不同種類的東西。</p>

    <p>變數值（value）有數種<em>資料型態（Data type）</em>。</p>
  </div>
</div>

------

```
var count = 0;
```

`count` 抽屜裡放數字；

`count` 屬於 `Number` 這個 Javascript 資料型態。

---

常見資料型態
----------

<div class="row">
  <div class="span4 centered">
    <table border="1">
      <tr>
        <td>`Boolean`</td>
        <td>真假值（`true` 或 `false`）</td>
      </tr>
      <tr>
        <td>`Number`</td>
        <td>數字（小數 / 浮點數）</td>
      </tr>
      <tr>
        <td>`String`</td>
        <td>字串</td>
      </tr>
      <tr>
        <td>`Object`</td>
        <td>物件。Javascript 有一些特殊的物件，如陣列（`Array`）以及日期物件（`Date`）。</td>
      </tr>
    </table>
  </div>
</div>

[(MDN) Javascript Data Structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)

---

複習 & 小細節
----------

* `var` ：「我有一個變數叫......」
* 變數名稱大小寫有差
* 設定運算子 `=`、四則運算、比大小運算子

[[mrorz-js-var?javascript,console]]

* 變數可以是任何型態的東西<br>`var a = 3` 裡頭， `a` 的型態會是 `number`
* Javascript 為動態型別（dynamically typed）語言
