HTTP
----------

A piece of code is worth a thousand words.

[Commit](https://github.com/NTU-CCSP/node-tutorial/commit/164159c82241cffd67515201ebc1adfbc4471025)
```JavaScript
var http = require('http');

http.createServer(function (req, res) {
    res.statusCode = 200;// 304
    res.end('fromHttpServer');
}).listen(5000);
```

* [http.createServer](http://nodejs.org/api/http.html#http_http_createserver_requestlistener)

---



HTTP Request
---

還記得[上禮拜](http://ccsp.ntumobile.org/tutorial/http.html#/0/3)也有講到

[Commit](https://github.com/NTU-CCSP/node-tutorial/commit/a8ec890e3f9bbc7c0d1c1698703d50a92ffdeca5)
```JavaScript
var http = require('http');
var host = '127.0.0.1';

http.createServer(function (req, res) {
    console.log(req.method + ' ' + req.url + ' HTTP/' + req.httpVersion);
    console.log('Host:' + host);
}).listen(5000, host);
```

* [http.IncomingMessage](http://nodejs.org/api/http.html#http_http_incomingmessage)
* [message.url](http://nodejs.org/api/http.html#http_message_url)

---



HTTP Response
---

[上禮拜](http://ccsp.ntumobile.org/tutorial/http.html#/0/4)也有講到

[Commit](https://github.com/NTU-CCSP/node-tutorial/commit/c58eac4870d1f745f0fb3613dbca6fade0121284)
```JavaScript
res.statusCode = 200;
res.setHeader('Content-Type', 'text/html');

var body = 
'<html>'+
'<head>'+
  '<title>An Example Page</title>'+
'</head>'+
'<body>'+
  'Hello World, this is a very simple HTML document.'+
'</body>'+
'</html>'

res.setHeader('Content-Length', body.length);
res.end(body);
```

* [http.ServerResponse](http://nodejs.org/api/http.html#http_class_http_serverresponse)
* [respond.end](http://nodejs.org/api/http.html#http_response_end_data_encoding)

---



Everything is Asynchronous
---

[Commit](https://github.com/NTU-CCSP/node-tutorial/commit/64d1ce1a32ece63762bfb017290dfaa55c46472f)
```JavaScript
var port = 5000;

console.log('before calling http.createServer');
http.createServer(function (req, res) {
    console.log(req.method + ' ' + req.url + ' HTTP/' + req.httpVersion);
    res.end('ok');
}).listen(port, host, function () {
    console.log('HTTP server started at ' + host + ':' + port);
});
console.log('http.createServer and .listen called');
```

* [Callback](http://ccsp.ntumobile.org/tutorial/http.html#/3/5)
* [server.listen](http://nodejs.org/api/http.html#http_server_listen_port_hostname_backlog_callback)

---

