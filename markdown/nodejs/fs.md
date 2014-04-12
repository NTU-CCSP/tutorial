File System
----------

* Another place to deal with asynchronous APIs
* However, they do provide synchronous versions. (postfixed with `*Sync`)

* [fs.readFile](http://nodejs.org/api/fs.html#fs_fs_readfile_filename_options_callback)
* [fs.readFileSync](http://nodejs.org/api/fs.html#fs_fs_readfilesync_filename_options)

---



Callbacks
---

* The asynchronous form always take a completion callback as its last argument.
* The arguments passed to the completion callback depend on the method, 
* **but the first argument is always reserved for an exception.**

[File System](http://nodejs.org/api/fs.html#fs_file_system)

---



Read File Example
---

[Commit](https://github.com/NTU-CCSP/node-tutorial/commit/5bcf59fb24b33042b05b99f612b40ac8b2bb4858)
```JavaScript
var fs = require('fs');

fs.readFile('./package.json', function (err, data) {
  if (err) { throw err; }
  console.log('Your project name is ' + data.name + ' with keywords ' + data.keywords);
  // console.log('---');
  // console.log(data);
});
```

* [fs.readFile](http://nodejs.org/api/fs.html#fs_fs_readfile_filename_options_callback)
* [Buffer::toString](http://nodejs.org/api/buffer.html#buffer_buf_tostring_encoding_start_end)

---



Send JSON File to Client
---

[Commit](https://github.com/NTU-CCSP/node-tutorial/commit/99ad3d2be3a237f55b7e1be85fd0826a6344d56d)
```JavaScript
fs.readFile('./package.json', 'utf8', function (err, data) {
  if (err) { throw err; }
  res.setHeader('Content-Type', 'application/json');
  res.end(data);
});
```

* [JSON formatter Chrome Extension](https://chrome.google.com/webstore/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa)

---



List Files Example
---

[Commit](https://github.com/NTU-CCSP/node-tutorial/commit/116a79accef33e0983f06571dc3b6a664e7108f9)

* [fs.readdir](http://nodejs.org/api/fs.html#fs_fs_readdir_path_callback)
* [fs.stat](http://nodejs.org/api/fs.html#fs_fs_stat_path_callback)
* [fs.Stats](http://nodejs.org/api/fs.html#fs_class_fs_stats)

---



File Upload Form
---

[Commit](https://github.com/NTU-CCSP/node-tutorial/commit/b0f5be5167c3a34360dd3d065328cab9f10a6249)

* [url.parse](http://nodejs.org/api/url.html#url_url_parse_urlstr_parsequerystring_slashesdenotehost)
* [multipart/form-data](http://www.w3.org/TR/html401/interact/forms.html#h-17.13.4.2)
* [fs.writeFile](http://nodejs.org/api/fs.html#fs_fs_writefile_filename_data_options_callback)
* [String::replace](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace)

<p class="fragment">What if I want to add more routes?</p>
<p class="fragment">Or output dynamic contents not just only simple length!</p>
<p class="fragment">It's a mess!</p>


