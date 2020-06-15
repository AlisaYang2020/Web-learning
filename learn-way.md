# HTML
## HTML 文档是由 HTML 元素定义的
HTML 元素以开始标签起始

HTML 元素以结束标签终止

元素的内容是开始标签与结束标签之间的内容

某些 HTML 元素具有空内容（empty content）

空元素在开始标签中进行关闭（以开始标签的结束而结束）

大多数 HTML 元素可拥有属性


## HTML 文档由嵌套的 HTML 元素构成

```shell
<html>

<body>
<p>This is my first paragraph.</p>
</body>

</html>
```
`<p>` 元素定义了 HTML 文档中的一个段

元素内容是：This is my first paragraph

`<body>` 元素定义了 HTML 文档的主体。

元素内容是另一个 HTML 元素（p 元素）。

`<html>` 元素定义了整个 HTML 文档。

元素内容是另一个 HTML 元素（body 元素）。

`style` 属性: 提供了一种改变所有 HTML 元素的样式的通用方法

**HTML参考手册：** https://www.w3school.com.cn/tags/index.asp


## HTML文本格式化

加粗、字号、斜体、上下标、强调、增删字

`<b>`加粗； `<strong>`加重语气。注意二者区别
`<i>`斜体；`<em>`强调。注意二者区别

`<pre>`预格式文本。它保留了编辑的空格和换行。适合显示计算机代码.

**块引用：**
`<blockquote>`定义常引用，浏览器会插入换行和外边距；`<q>`定义短引用，不会有特殊呈现。

**改变文本的外观和含义**

很多标签都可以用来改变文本的外观，并为文本关联其隐藏的含义。这些标签可分为基于内容的样式、物理样式。

基于内容的样式标签会告诉浏览器它所包含的文本具有特定的含义、上下文或者用法。然后浏览器就会把与该含义、上下文或者用法一致的格式应用在文本上。请注意这里面的区别。**基于内容的标签赋予含义，而不是格式化。**

在使用 HTML 或 XHTML 时，除非极少情况下，都应该避免使用物理标签。应当尽可能地向浏览器提供上下文信息，并使用基于内容的样式。

### HTML计算机代码元素

`<code>`元素不保留多余的空格和折行，解决该问题，在内加入 `<pre> `元素包围代码。


## HTML CSS

当浏览器读到一个样式表，它就会按照这个样式表来对文档进行格式化

### 外部样式表

当样式需要被应用到很多页面的时候，使用外部样式表，就可以通过更改一个文件来改变整个站点的外观。
```shell
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```
### 内部样式表

当单个文件需要特别样式时，可以在 head 部分通过 <style> 标签定义内部样式表。
  ```shell
  <head>
  <style type="text/css">
  body {background-color: red}
  p {margin-left: 20px; color: blue}
  </style>
  </head>
  ```
  
### 内联样式
当特殊的样式需要应用到个别元素时，可以在相关的标签中使用样式属性。样式属性可以包含任何 CSS 属性。以下实例显示出如何改变段落的颜色和左外边距。
```shell
<p style="color: red; margin-left: 20px">
This is a paragraph
</p>
```

## HTML超链接
 `href` 属性(链接别人) - 创建指向另一个文档的链接
 
 `name` 属性（被别人链接） - 创建文档内的书签(使用命名锚（named anchors）时，我们可以创建直接跳至该命名锚（比如页面中某个小节）的链接)
 ```shell
 <a name="tips">基本的注意事项 - 有用的提示</a>
 <a href="#tips">有用的提示</a>
 
 //在其他页面中创建指向该锚的链接:# 符号和锚名称添加到 URL 的末端
 <a href="http://www.w3school.com.cn/html/html_links.asp#tips">有用的提示</a>
 ```
 
 使用  `Target` 属性，定义被链接的文档在何处显示:新窗口 or 当前窗口
```shell
<a href="http://www.w3school.com.cn/" target="_blank">Visit W3School!</a>
```

**注意：** 假如页面被固定在框架之内 `target="_top"` 跳出框架，在当前窗口显示。


