# Node.js 實作：基於 markdown 的電子書出版系統

## Markdown 模組

showdown : 將 markdown 轉換為 html 最常被用的程式
pagedown : stackoverflow 所使用的 markdown 轉換程式，從 showdown 修改而來
marked     強調速度的 markdown 轉 html 程式
markx    : 結合 markdown 與 jade 模板引擎的專案。

## marked 轉換套件

首先，請從下列網址下載 marked.js 這個檔案，然後與下列的測試程式放在同一個資料夾中，這樣測試程式才能順利引用到此模組。

* https://github.com/chjj/marked/blob/master/lib/marked.js

程式：markedTest.js

```javascript
marked = require('./marked');

// Set default options
marked.setOptions({
  gfm: true,
  tables: true,
  breaks: false,
  pedantic: false,
  sanitize: true,
  smartLists: true,
  langPrefix: 'language-',
  highlight: function(code, lang) {
    if (lang === 'js') {
      return highlighter.javascript(code);
    }
    return code;
  }
});

console.log(marked('i am using __markdown__.'));
```

執行結果：

```
D:\code\node>node markedTest.js
<p>i am using <strong>markdown</strong>.</p>
```

接下來就可以實作完整的轉換程式 md2htm 了，該程式的參數有兩個，執行方式如下：

* node md2htm <markdown input file> <html output file>

程式：md2htm.js

```javascript
var marked = require('./marked');
var fs = require('fs');
var argv = process.argv;
var md = fs.readFileSync(process.argv[2], "utf8");

// Set default options
marked.setOptions({
  gfm: true,
  tables: true,
  breaks: false,
  pedantic: false,
  sanitize: true,
  smartLists: true,
  langPrefix: 'language-',
  highlight: function(code, lang) {
    if (lang === 'js') {
      return highlighter.javascript(code);
    }
    return code;
  }
});

var html = marked(md);

fs.writeFileSync(process.argv[3], html, "utf8");
```

執行結果

```
D:\code\node>node md2htm.js test.md test.html
```

## Markdown 動態網頁編輯器

.... 等待撰寫中 .....


## 參考文獻
* http://stackoverflow.com/questions/134235/is-there-any-good-markdown-javascript-library-or-control
    * Jquery-Markedit - This was forked from wmd-edit quite some time ago and refactored to use jQuery. Seems good at first sight.
    * EpicEditor - is also still maintained, has a flexible parser and, as you can see below, the author is highly responsive (see below). IT seems to have good documentation as well. Sadly not working with IE9.
    * MarkdownDeep is a third option that is still current. The interesting point with this one is support for Markdown Extra. Has a dependency on JQuery (actually you can also implement without JQuery). Based on the .NET version so documentation is more aligned to that than the JS version. This also works with IE9. It is very easy to use (with JQuery) & very simple. No significant development happening with this though as far as I can see.
    * js-markdown-extra is a fairly accurate port of the PHP library and is still under maintenance. It supports Markdown Extra of course.
* https://github.com/coreyti/showdown
* https://code.google.com/p/pagedown/
    * Stackoverflow 所使用的 markdown 轉 html 引擎。
    * <https://code.google.com/p/pagedown/wiki/PageDown>
* https://github.com/jgallen23/markx
    * <http://thechangelog.com/markx-convert-markdown-jade-and-more-to-static-html-with/>
* https://github.com/andris9/node-markdown
* https://github.com/chjj/marked
