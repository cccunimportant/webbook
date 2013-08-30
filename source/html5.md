# 新一代網頁語法 -- HTML 5

## HTML 5 簡介
HTML 5 最早是由由 WHATWG 在 2004 年提出，2007年被 W3C 所接納，在2008年1月22日發布第一份正式草案，預計在 2012 年才會推出正式標準。

即便如此，各家瀏覽器廠商早已展開動作，紛紛將 HTML5 視為重要的戰場，Firefox、Opera、Google Chrome、Apple Safari 等瀏覽器都已經支援了 HTML5 的功能，微軟的 IE 可以說是最慢才宣布要支援 HTML5 的重要瀏覽器，但微軟也已明確宣布要在 IE9 當中全力擁抱 HTML5，這些現象讓 HTML5 可能成為下一代 Web 的最重要技術。

目前在 Web 上，關於繪圖等功能主要是採用 Adobe 的 Flash 技術所製作的，但是在 iPhone 成功佔領手機市場後，蘋果的老板 Steve Job 卻拒絕讓 Flash 登上 iPhone 平台，並且聲稱 HTML5 比 Flash 好太多了。Steve Jobs 更進一步以契約的方式借助法律規定任何 Flash 技術都不准登上 iPhone 平台，這個動作對 Flash 技術的殺傷力極大，但也讓 HTML5 陣營的氣勢大盛，網路上紛紛盛傳 Flash 即將死亡，HTML5 將取而代之。

技術體系：

HTML 5 是新一代的網頁標準，其內涵並非只有 HTML5 一項而已，整個技術體系包含 HTML5、CSS3 與增強過的 JavaScript API 函式庫，這個架構可以用下列公式表示。

	HTML5 = HTML5 + CSS3 + new JavaScript API

在上述公式中，最重要的角色其實是 new JavaScript API，因為這個新版的函式庫當中包含了 2D 的 Canvas 繪圖、3D 的 WebGL 技術、衛星定位函式庫、網路的 Socket 函式庫、WebSQL 資料庫函數、以及 local Storage 函數可用來永久儲存資料，這些技術讓瀏覽器能力大為增強，幾乎可以成為網路作業系統了。

目前 HTML5 的標準尚未定案，但是各家瀏覽器廠商已經開始大幅支援 HTML5 標準了，這使得實作可能會比標準領先，因而也會進一步改變 HTML5 的技術內容，形成更完整的網頁呈現體系，筆者相信在這兩年當中，HTML5 仍會有不少的修改與進化，而非是一成不變的。

## HTML 4 語法的簡化與修改

### 簡化：檔頭

簡化前：HTML4

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```

簡化後：HTML5

```html
<!DOCTYPE html>
```

### 簡化：JavaScript 引用

簡化前：HTML4

```html
<link rel="stylesheet" href="path/to/stylesheet.css" type="text/css" />
<script type="text/javascript" src="path/to/script.js"></script>
```

簡化後：HTML5

```html
<link rel="stylesheet" href="path/to/stylesheet.css" />
<script src="path/to/script.js"></script>
```

### 修改：Small 標記的意義

Small 標記原來代表副標題，現在用來代表小字或邊註。

### 修改：屬性可以不加引號

```html
<p class=myClass id=someId> Start the reactor.
```

### 新增：email 型態的輸入欄位

```html
<input id="email" name="email" type="email" />
```

### 新增：Placeholder

```html
<input name="email" type="email" placeholder="doug@givethesepeopleair.com" />
```

### 新增：Required 屬性

```html
<input type="text" name="someInput" required>
```

```html
<input type="text" name="someInput" required="required">
```

### 新增：Autofocus

```html
<input type="text" name="someInput" placeholder="Douglas Quaid" required autofocus>
```

### 新增：正則表達式

```html
<form action="" method="post">
<label for="username">Create a Username: </label>
<input type="text" name="username" id="username" placeholder="4 <> 10"
pattern="[A-Za-z]{4,10}" autofocus required>
<button type="submit">Go </button>
</form>
```

### 新增：Mark

Mark 用來標註那些需要凸顯的字詞，像是以下的 "Open Your Mind"

```html
<h3> Search Results </h3>
<p> They were interrupted, just after Quato said, <mark>"Open your Mind"</mark>. </p>
```

## 結構性語意標記
HTML4 ：目前的部落格描述方式
問題：有太多的 div 標記，很難用程式解析其語意關係。

```html
<html>
  <head>
    <title>Mokka mit Schlag </title>
 </head>
<body>
<div id="page">
  <div id="header">
    <h1><a href="http://www.elharo.com/blog">Mokka mit Schlag</a></h1>
  </div>
  <div id="container">
    <div id="center" class="column">               
      <div class="post" id="post-1000572">
        <h2><a href=
      "/blog/birding/2007/04/23/spring-comes-and-goes-in-sussex-county/">
      Spring Comes (and Goes) in Sussex County</a></h2>
        
        <div class="entry">
          <p>Yesterday I joined the Brooklyn Bird Club for our
          annual trip to Western New Jersey, specifically Hyper
          Humus, a relatively recently discovered hot spot. It
          started out as a nice winter morning when we arrived
          at the site at 7:30 A.M., progressed to Spring around
          10:00 A.M., and reached early summer by 10:15. </p>
        </div>
      </div>


      <div class="post" id="post-1000571">
        <h2><a href=
          "/blog/birding/2007/04/23/but-does-it-count-for-your-life-list/">
           But does it count for your life list?</a></h2>
        
        <div class="entry">
          <p>Seems you can now go <a
          href="http://www.wired.com/science/discoveries/news/
          2007/04/cone_sf">bird watching via the Internet</a>. I
          haven't been able to test it out yet (20 user
          limit apparently) but this is certainly cool.
          Personally, I can't imagine it replacing
          actually being out in the field by any small amount.
          On the other hand, I've always found it quite
          sad to meet senior birders who are no longer able to
          hold binoculars steady or get to the park. I can
          imagine this might be of some interest to them. At
          least one elderly birder did a big year on TV, after
          he could no longer get out so much. This certainly
          tops that.</p>
        </div>
      </div>

      </div>
    
    <div class="navigation">
      <div class="alignleft">
         <a href="/blog/page/2/">&laquo; Previous Entries</a>
       </div>
      <div class="alignright"></div>
    </div>
  </div>

  <div id="right" class="column">
    <ul id="sidebar">
      <li><h2>Info</h2>
      <ul>
        <li><a href="/blog/comment-policy/">Comment Policy</a></li>
        <li><a href="/blog/todo-list/">Todo List</a></li>
      </ul></li>
      <li><h2>Archives</h2>
        <ul>
          <li><a href='/blog/2007/04/'>April 2007</a></li>
          <li><a href='/blog/2007/03/'>March 2007</a></li>
          <li><a href='/blog/2007/02/'>February 2007</a></li>
          <li><a href='/blog/2007/01/'>January 2007</a></li>
        </ul>
      </li>
    </ul>
  </div>
  <div id="footer">
    <p>Copyright 2007 Elliotte Rusty Harold</p>
  </div>
</div>
  
</body>
</html>
```

HTML5 ：新的部落格描述方式
解決：改用 section, article 的方式，以釐清哪些是文章，哪些是段落。

```html
<html>
 <head>
    <title>Mokka mit Schlag </title>
 </head>
<body>
  <header>
    <h1><a href="http://www.elharo.com/blog">Mokka mit Schlag</a></h1>
  </header>
  <section>               
      <article>
        <h2><a href=
        "/blog/birding/2007/04/23/spring-comes-and-goes-in-sussex-county/">
         Spring Comes (and Goes) in Sussex County</a></h2>
        
        <p>Yesterday I joined the Brooklyn Bird Club for our
        annual trip to Western New Jersey, specifically Hyper
        Humus, a relatively recently discovered hot spot. It
        started out as a nice winter morning when we arrived at
        the site at 7:30 A.M., progressed to Spring around 10:00
        A.M., and reached early summer by 10:15. </p>
      </article>


      <article>
        <h2><a href=
          "/blog/birding/2007/04/23/but-does-it-count-for-your-life-list/">
          But does it count for your life list?</a></h2>
        
          <p>Seems you can now go <a
          href="http://www.wired.com/science/discoveries/news/
          2007/04/cone_sf">bird watching via the Internet</a>. I
          haven't been able to test it out yet (20 user
          limit apparently) but this is certainly cool.
          Personally, I can't imagine it replacing
          actually being out in the field by any small amount.
          On the other hand, I've always found it quite
          sad to meet senior birders who are no longer able to
          hold binoculars steady or get to the park. I can
          imagine this might be of some interest to them. At
          least one elderly birder did a big year on TV, after
          he could no longer get out so much. This certainly
          tops that.</p>
      </article>    
    <nav>
      <a href="/blog/page/2/">&laquo; Previous Entries</a>
    </nav>
  </section>

  <nav>
    <ul>
      <li><h2>Info</h2>
      <ul>
        <li><a href="/blog/comment-policy/">Comment Policy</a></li>
        <li><a href="/blog/todo-list/">Todo List</a></li>
      </ul></li>
      <li><h2>Archives</h2>
        <ul>
          <li><a href='/blog/2007/04/'>April 2007</a></li>
          <li><a href='/blog/2007/03/'>March 2007</a></li>
          <li><a href='/blog/2007/02/'>February 2007</a></li>
          <li><a href='/blog/2007/01/'>January 2007</a></li>
        </ul>
      </li>
    </ul>
  </nav>
  <footer>
    <p>Copyright 2007 Elliotte Rusty Harold</p>
  </footer>
  
</body>
</html>
```

檢視範例：<http://dl.dropbox.com/u/6387819/html5/Semantics/TagStructure.htm>

## 互動性標記

標記：更詳細資訊 - details

預設不會顯示的進一步資訊

```html
The bill of a Craveri's Murrelet is about 10% thinner than
the bill of a Xantus's Murrelet.
<details>
<legend>[Sibley, 2000]</legend>
<p>Sibley, David Allen, The Sibley Guide to Birds, (New York:
Chanticleer Press, 2000) p. 247 </p>
</details>
```

## 標記：表格資料 - datagrid
```html
<datagrid>
  <table>
    <tr><td>Jones</td><td>Allison</td><td>A-</td><td>B+</td><td>A</td></tr>
    <tr><td>Smith</td><td>Johnny</td><td>A</td><td>C+</td><td>A</td></tr>
    <tr><td>Willis</td><td>Sydney</td><td>C-</td><td>D</td><td>F</td></tr>
    <tr><td>Wilson</td><td>Frank</td><td>B-</td><td>B+</td><td>A</td></tr>
  </table>
</datagrid>
```

```
interface HTMLDataGridElement : HTMLElement {
           attribute DataGridDataProvider data;
  readonly attribute DataGridSelection selection;
           attribute boolean multiple;
           attribute boolean disabled;
  void updateEverything();
  void updateRowsChanged(in RowSpecification row, in unsigned long count);
  void updateRowsInserted(in RowSpecification row, in unsigned long count);
  void updateRowsRemoved(in RowSpecification row, in unsigned long count);
  void updateRowChanged(in RowSpecification row);
  void updateColumnChanged(in unsigned long column);
  void updateCellChanged(in RowSpecification row, in unsigned long column);
};
```

```
interface DataGridDataProvider {
  void initialize(in HTMLDataGridElement datagrid);
  unsigned long getRowCount(in RowSpecification row);
  unsigned long getChildAtPosition(in RowSpecification parentRow,
      in unsigned long position);
  unsigned long getColumnCount();
  DOMString getCaptionText(in unsigned long column);
  void getCaptionClasses(in unsigned long column, in DOMTokenList classes);
  DOMString getRowImage(in RowSpecification row);
  HTMLMenuElement getRowMenu(in RowSpecification row);
  void getRowClasses(in RowSpecification row, in DOMTokenList classes);
  DOMString getCellData(in RowSpecification row, in unsigned long column);
  void getCellClasses(in RowSpecification row, in unsigned long column,
      in DOMTokenList classes);
  void toggleColumnSortState(in unsigned long column);
  void setCellCheckedState(in RowSpecification row, in unsigned long column,
      in long state);
  void cycleCell(in RowSpecification row, in unsigned long column);
  void editCell(in RowSpecification row, in unsigned long column, in DOMString data);
};
```

+ 標記：功能選單 - menu 與 command

```html
<menu>
    <command onclick="alert('first command')"  label="Do 1st Command"/>
    <command onclick="alert('second command')" label="Do 2nd Command"/>
    <command onclick="alert('third command')"  label="Do 3rd Command"/>
</menu>
```

```
<menu type="toolbar">
    <command onclick="insertTag(buttons, 0);"  label="strong" icon="bold.gif"/>
    <command onclick="insertTag(buttons, 1);"  label="em" icon="italic.gif"/>
    <command onclick="insertLink(buttons, 2);" label="link" icon="link.gif"/>
    <command onclick="insertTag(buttons, 3);"  label="b-quote" icon="blockquote.gif"/>
    <command onclick="insertTag(buttons, 4);"  label="del" icon="del.gif"/>
    <command onclick="insertTag(buttons, 5);"  label="ins" icon="insert.gif"/>
    <command onclick="insertImage(buttons);"   label="img" icon="image.gif"/>
    <command onclick="insertTag(buttons, 7);"  label="ul" icon="bullet.gif"/>
    <command onclick="insertTag(buttons, 8);"  label="ol" icon="number.gif"/>
    <command onclick="insertTag(buttons, 9);"  label="li" icon="item.gif"/>
    <command onclick="insertTag(buttons, 10);" label="code" icon="code.gif"/>
    <command onclick="insertTag(buttons, 11);" label="cite" icon="cite.gif"/>
    <command onclick="insertTag(buttons, 12);" label="abbr" icon="abbr.gif"/>
    <command onclick="insertTag(buttons, 13);" label="acronym" icon="acronym.gif"/>
</menu>
```

```
<menu type="popup" label="Edit">
    <command onclick="undo()"   label="Undo"/>
    <command onclick="redo()"   label="Redo"/>
    <command onclick="cut()"    label="Cut"/>
    <command onclick="copy()"   label="Copy"/>
    <command onclick="paste()"  label="Paste"/>
    <command onclick="delete()" label="Clear"/>
</menu>
```

檢視結果：<http://dl.dropbox.com/u/6387819/html5/menu.htm>

## 結語
假如 HTML5 真的大為流行，那麼就會形成一個跨平台的程式開發環境，這個平台將會跨越電腦、筆電、平板電腦、手機、PDA 等裝置。因此，您只要開發一個 HTML5 的網站，就可以讓所有上網裝置都可以使用您所開發的功能，這對程式設計師而言無疑有極大的魅力。

由於 HTML5 已經讓瀏覽器具有網路作業系統的潛能，因此您的網站其實就是一個應用程式，而這個應用程式可以做 2D、3D 繪圖、衛星定位、存取資料庫等工作，您可以輕易的寫出多人網路線上 GPS 遊戲，以及大部分您在桌上型電腦所能寫出的應用程式，這實在是相當令人期待的一件事啊！


## 參考文獻
* The HTML5 test - How well does your browser support HTML5? -- <http://html5test.com/>
* apple html5 (Apple 的 HTML5 推廣網站) -- <http://www.apple.com/html5/>
* HTML5rocks -- <http://www.html5rocks.com/>
	* HTML5 教學投影片 -- <http://slides.html5rocks.com/#slide1>
	* Google Html5rocks Playground -- <http://playground.html5rocks.com/>
	* HTML5rocks Tutorial -- <http://www.html5rocks.com/tutorials/>
* HTML 5的5個相關網站 -- <http://www.inside.com.tw/04/08/5sites-about-html5>
	* <http://html5demos.com/ HTML 5 Demos and Examples]
	* <http://canvaspaint.org/ Canvas Paint]
	* <http://html5gallery.com/ HTML5 Gallery]
	* <http://html5tutorial.net/ HTML5 Tutorial]
	* <http://www.youtube.com/html5 YouTube]
* RipCode 會是Flash在蘋果世界的救星嗎？ -- <http://mag.udn.com/mag/digital/storypage.jsp?f_MAIN_ID=322&f_SUB_ID=2920&f_ART_ID=244207>
*  HTML 5 預覽 -- <http://www.mox.tw/forum/viewthread.php?tid=499>
* Google I/O大會第一天：HTML5應用大放異彩 -- <http://mag.udn.com/mag/digital/storypage.jsp?f_MAIN_ID=320&f_SUB_ID=2943&f_ART_ID=249031>
* Google I/O 2010 - Keynote Day 1 - Full Length -- <http://www.youtube.com/watch?v=a46hJYtsP-8&feature=channel>
* <http://zh.wikipedia.org/zh/HTML_5>
