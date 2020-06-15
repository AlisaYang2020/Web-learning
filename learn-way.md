# HTML
### HTML 文档是由 HTML 元素定义的
HTML 元素以开始标签起始

HTML 元素以结束标签终止

元素的内容是开始标签与结束标签之间的内容

某些 HTML 元素具有空内容（empty content）

空元素在开始标签中进行关闭（以开始标签的结束而结束）

大多数 HTML 元素可拥有属性

### HTML 文档由嵌套的 HTML 元素构成

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

**HTML参考手册：**https://www.w3school.com.cn/tags/index.asp

### HTML文本格式化

加粗、字号、斜体、上下标、强调、增删字

`<b>`加粗； `<strong>`加重语气。注意二者区别
`<i>`斜体；`<em>`强调。注意二者区别

`<pre>`预格式文本。它保留了编辑的空格和换行。适合显示计算机代码.

**块引用：**
`<blockquote>`定义常引用，浏览器会插入换行和外边距；`<q>`定义短引用，不会有特殊呈现。


