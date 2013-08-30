# jQuery 套件

## jQuery 的第一個程式範例

```html
<html>
 <head>
  <SCRIPT language="JavaScript" SRC="jquery.js"></SCRIPT>
 </head>
 <body>
  <script type="text/javascript">
  $(function() {
    document.write("Hello jQuery !");
  });
  </script>
 </body>
</html>
```

執行結果

![](../img/jqhello.png)

## jQuery 的 each 函數

範例程式

```html
<html>
 <head>
  <SCRIPT language="JavaScript" SRC="jquery.js"></SCRIPT>
 </head>
 <body>
  <b id="bold1">bold</b><BR/>
  <a id="link1" href="http://www.yahoo.com/">Yahoo</a><BR/>
  <script type="text/javascript">
  $('*').each(function(i) {
    document.write("node "+i+":nodeName="+this.nodeName+" id="+this.id+"<br/>");
  });
  </script>
 </body>
</html>
```

執行結果

![](../img/jqeach.png)

## jQuery 篩選器


## jQuery 的 AJAX 功能

程式：jqload.htm

```html
<html>
 <head>
  <SCRIPT language="JavaScript" SRC="jquery.js"></SCRIPT>
 </head>
 <body>
  <div id="txtbox" style="border:solid 1px; width:100%; height:200px;">
  </div>
  <script type="text/javascript">
  $('#txtbox').load('hello.txt');
  </script>
 </body>
</html>
```

檔案：hello.txt

```
Hello, jQuery ! 
Hello, AJAX !
```

執行結果

![](../img/jqload.png)

