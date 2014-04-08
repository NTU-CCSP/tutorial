Form
---

Simpest way interact with user.

![form](images/http/form.png)

---

In Code
---
Basic sytax like this

```
<form action="URL" method="{post, get}" >
  input element
</form>

```

`action`: 表單要送到的地方。 `method`: 用什麼方法送。

---

[[form-example]]
`type="submit"`: 根據 form 的 attribute 提交問卷。
`type="reset"`: 清空 form 裡的所填的值。  
`placeholder`: 暫時顯示在表單內的內容，作為提示之用。
`name`: 給欄位名字，讓 Server 讀取。

---

Get example
---

[[form-get-example]]

---

Post example
---

[[form-post-example]]

---

![compare with get and post](images/http/get_post.png)

---

##enctype

當使用 `post` 方法傳輸時，可以傳輸不只是單純文字的資料

[[form-post-example]]

- `application/x-www-form-urlencoded`: 預設值，空白會被轉換為`+`，特殊字元會被轉換為 ASCII 十六進位表示。
- `multipart/form-data`: 配合 `<input type="file">` 可以上傳檔案。
- text/plain: HTML5 新增，純文字表示。

---

Multipart example
---

[[form-file-example]]
