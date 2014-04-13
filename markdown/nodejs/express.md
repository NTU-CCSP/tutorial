Comes to rescue
----------

* routing problem
* static files serving
* dynamic view rendering
* **middleware** !?

---



Initialize
---

<ul>
  <li class="fragment">`npm install express@3.x.x --save` **3.x.x** is very **IMPORTANT**</li>
  <li class="fragment">`var express = require('express');`</li>
  <li class="fragment">Wait! `require` works here?</li>
</ul>

---



Module
---

The Module System has three type of modules :
<ul>
  <li class="fragment">[Core Modules](http://nodejs.org/api/modules.html#modules_core_modules) : http, fs, url</li>
  <li class="fragment">[File Modules](http://nodejs.org/api/modules.html#modules_file_modules) : index.js, package.json</li>
  <li class="fragment">[Loading from `node_modules` folders](http://nodejs.org/api/modules.html#modules_loading_from_node_modules_folders) : express, q</li>
</ul>

<div class="fragment">[require Module are CACHED](http://nodejs.org/api/modules.html#modules_caching)</div>

---



Usage
---

[Commit](https://github.com/NTU-CCSP/node-tutorial/commit/bff8c45432244ed602ad532a0c184283bc6ab3d0)

API docs => [express.js@3.x.x](http://expressjs.com/3x/api.html)

* [app.use](http://expressjs.com/3x/api.html#app.use)
* [express.bodyParser](http://expressjs.com/3x/api.html#bodyParser)
* [res.sendfile](http://expressjs.com/3x/api.html#res.sendfile)
* [app.get](http://expressjs.com/3x/api.html#app.get)

---



Template Engine
---

* [ejs](https://github.com/visionmedia/ejs) : Embedded JavaScript
* `npm install ejs`
* `app.set('view engine', 'ejs');`
* put your `.ejs` under `views` directory
* call `res.render` to generate HTML

[Commit](https://github.com/NTU-CCSP/node-tutorial/commit/72c48bd2f105e4b095085a19c7f479bc1285ced1)

---



Includes for common parts
---

* It's annoying to write duplicated HTMLs
* Let's extract them using [`include`](https://github.com/visionmedia/ejs#includes)

```HTML
<head>
  <meta charset="utf-8">
  <title><%= title %></title>
</head>
```
[Commit](https://github.com/NTU-CCSP/node-tutorial/commit/9f895f1523d884eaef3853b7386694cadcbb9b47)

---



Extract Controller Codes
---

<ul>
  <li>What's controller?</li>
  <li class="fragment">It handles request and provides response for client</li>
  <li class="fragment">Use [`module.exports`](http://nodejs.org/api/modules.html#modules_module_exports) to create controller module</li>
</ul>

[Commit](https://github.com/NTU-CCSP/node-tutorial/commit/b8b2b5a0bb7fc5e3a5ad2ef47ec9a4645719fc8a)

---

The MVC Pattern
---

<ul>
  <li>[Model–view–controller](http://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller) (MVC) is a software pattern for implementing user interfaces.</li>
  <li class="fragment">So we have `views` and `controllers`, what about `models`?</li>
</ul>

---



Models
---

* Use a Database such as `MySQL` or `MongoDB`
* Use [File System](http://nodejs.org/api/fs.html#fs_file_system) to read/save data
* [fs](http://nodejs.org/api/fs.html#fs_file_system) with relative files writes to [`process.cwd`](http://nodejs.org/api/process.html#process_process_cwd)

[Commit](https://github.com/NTU-CCSP/node-tutorial/commit/9e05534a4bc7125a938872e1b67a3294adc64b8e)

---



Extract Model Codes
---

* Model(data) is the core of applications
* We may use it again and agian everywhere in applications
* Extracting them to independent module is always a good idea

[Commit](https://github.com/NTU-CCSP/node-tutorial/commit/a806d35fe8182edb9968fe6a632c76b91c13a8b4)

---



剩下就是你們的事了
---


