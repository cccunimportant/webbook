
## Cookie 與 Session 的處理

... 本節尚待整理撰寫中 ....

* 參考：http://www.hacksparrow.com/sessions-in-express-js-node-js-web-framework.html

$ npm install express -g

Then, create an app with sessions support:

$ express --sessions

The session object is attached to the HTTP request object, just read from it or write to it. Here is an example of handling session in Express:

```javascript
app.post('/', function(req, res) {
    if (req.session.logged) res.send('Welcome back!');
    else {
        req.session.logged = true;
        res.send('Welcome!');
    }
};
```

* http://fred-zone.blogspot.tw/2011/11/nodejs-express-cookie-based-session.html

可以直接使用 npm 安裝：

npm install cookie-sessions

在你的 app.js 這樣使用：

```javascript
var express = require('express');
var CookieStore = require('cookie-sessions');

var app = module.exports = express.createServer();

app.configure(function(){
 app.set('views', __dirname + '/views');
 app.set('view engine', 'jade');
 app.use(express.bodyParser());
 app.use(express.methodOverride());
 app.use(express.cookieParser());
 app.use(CookieStore({ secret: 'FredChien' }));
 app.use(app.router);
 app.use(express.static(__dirname + '/public'));
});

app.get('/', function(req, res) {
 req.session = { email: 'cfsghost@gmail.com' };

 /* Redirect to another page */
 res.redirect('/getsession');
});

app.get('/getsession', function(req, res) {
 if (req.session)
  res.end('This is Fred's email address:' + req.session.email);
});

app.listen(3000);
```

## 參考實作：登入模組

* junwatu / nodejs-express-start
    * <https://github.com/junwatu/nodejs-express-start/tree/login-registration-app>
    * 展示影片：<http://www.youtube.com/watch?v=jGBbMVJx3h0>

* Building a Login System in Node.js and MongoDB
    * <http://www.quietless.com/kitchen/building-a-login-system-in-node-js-and-mongodb/>

上述實作使用到以下套件：

* Node.js - Application Server
* Express.js - Node.js Web Framework
* MongoDb - Database Storage
* mangoose -- NoSQL 資料庫 
*Jade - HTML Templating Engine
    * http://jade-lang.com/
* Stylus - CSS Preprocessor
    * http://learnboost.github.com/stylus/
* EmailJS - Node.js > SMTP Server Middleware
* Moment.js - Lightweight Date Library
* Twitter Bootstrap - UI Component & Layout Library

