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

## HTML图像标签
`align`所有标签中对齐方式的属性
`alt`替换文本

### 客户端图像映射

(1)在`<img>`中设置usemap属性。

(2)在`<map>`中设置name/id属性(二者属性值必须相同)
```shell
<img
src="/i/eg_planets.jpg"
usemap="#planetmap"
alt="Planets" />

<map name="planetmap" id="planetmap">

<area
shape="circle"
coords="180,139,14"//圆心，半径
href ="/example/html/venus.html"
target ="_blank"
alt="Venus" />

<area
shape="circle"
coords="129,161,10"
href ="/example/html/mercur.html"
target ="_blank"
alt="Mercury" />

<area
shape="rect"
coords="0,0,110,260"//矩形左上角，右下角
href ="/example/html/sun.html"
target ="_blank"
alt="Sun" />

</map>
```
`<area>`定义图像地图中的可点击区域，每个区域都是一个超链接

`<map>`img 元素中的 "usemap" 属性引用 map 元素中的 "id" 或 "name" 属性（根据浏览器），所以同时向 map 元素添加了 "id" 和 "name" 属性

### 服务器端图像映射

```shell
<a href="/example/html/html_ismap.html">
<img src="/i/eg_planets.jpg" ismap />
</a>
```
把鼠标移动到图像上或点击某处时，浏览器会显示鼠标坐标（相对于图像的左上角），或发送到服务器端。特殊的服务器端软件（在本例中是 /example/html/html_ismap.html 程序）可以根据这些坐标来做出响应。

**注意：**  只有当 <img> 元素属于带有有效 href 属性的 <a> 元素的后代时，才允许 ismap 属性。
 
## HEML表格、列表
表格：行列项目

`<col>` 元素是仅包含属性的空元素

为 `<colgroup>` 标签添加 class 属性。这样就可以使用 CSS 来负责对齐方式、宽度和颜色等等

`<thead><tfoot><tbody>`必须一起使用

列表：一列项目。

有序/无序列表：列表始于 `<ul>/<ol>` 标签。每个列表项始于 `<li>` 标签

自定义列表：不仅仅是一列项目，而是项目及其注释的组合。列表以`<dl>` 标签开始。每个自定义列表项以 `<dt>` 开始。每个自定义列表项的定义以 `<dd>` 开始。

## HTML 布局

`<div>`块级元素，定义文档中的分区或节，浏览器会在其前后显示折行。与 CSS 一同使用，可对大的内容块设置样式属性； 另一个常见的用途是文档布局。

常用作布局工具，因为能够轻松地通过 CSS 对其进行定位

`<span>`内联元素，组合文档中的行内元素，用作文本的容器。与 CSS 一同使用时，可为部分文本设置样式属性。

### HTML类
设置类，为元素的类定义 CSS 样式。为相同的类设置相同的样式，或者为不同的类设置不同的样式。
```shell
<html>
<head>
<style>
.cities { //块级类;用 . 是类，引用时用 class=""; 用 # 是命名锚，引用时用 id=""
    background-color:black;
    color:white;
    margin:20px;
    padding:20px;
} 

span.red {color: red;} //行内类

table.lamp { //表格类
    width:100%;
    border:1px solid #d4d4d4;
}
table.lamp th, td {
    padding:10px;
}
table.lamp td {
    width:40px;
}

</style>
</head>

<body>

<div class="cities">
<h2>London</h2>
<p>
London is the capital city of England. 
It is the most populous city in the United Kingdom, 
with a metropolitan area of over 13 million inhabitants.
</p>
</div> 

<h1>My <span class="red">Important</span> Heading</h1>

<table class="lamp">
<tr>
  <th>
    <img src="/images/lamp.jpg" alt="Note" style="height:32px;width:32px">
  </th>
  <td>
    The table element was not designed to be a layout tool.
  </td>
</tr>
</table>

</body>
</html>
```

## HTML响应式web设计
RWD 指的是响应式 Web 设计（Responsive Web Design）

RWD 能够以可变尺寸传递网页

RWD 对于平板和移动设备是必需的

1.自己创建； 2.使用Bootstrap（最流行的开发响应式 web 的 HTML, CSS, 和 JS 框架）

## HTML框架

**框架结构标签**`<frameset>`定义如何将窗口分割为框架
每个 frameset 定义了一系列行或列
rows/columns 的值规定了每行或每列占据屏幕的面积百分比

**框架标签**`<Frame>`定义了放置在每个框架中的 HTML 文档

<html>

<frameset cols="50%,50%">
  <frameset rows="30%,70%">
  	<frame src="/example/html/frame_b.html">
  	<frame src="/example/html/frame_c.html">
  </frameset>
	<frame src="/example/html/frame_a.html">

<noframes>
<body>您的浏览器无法处理框架！</body>
</noframes>

</frameset>

</html>

**重要提示：**不能将 `<body></body> `标签与 `<frameset></frameset>` 标签同时使用！不过，假如你添加包含一段文本的` <noframes> `标签，就必须将这段文字嵌套于`<body></body>` 标签内。


### 导航框架
主页面

```shell
<html>

<frameset cols="10%,90%">
	<frame src="index.html"></frame>
	<frame src="frame_a.html#h66" name="content"></frame> //#定位到对应页面的id为content的标签处
</frameset>

</html>
```
导航栏
```shell
<html>
<body>
<a href="frame_a.html" target="content">Frame a</a><br />
<a href="frame_b.html" target="content">Frame b</a><br />
<a href="frame_c.html" target="content">Frame c</a><br />
</body>
</html>
```
注意`name`和`target`对应，在目标框架内显示。

### 内联框架 iframe
在网页内显示网页

`iframe` 可用作链接的目标（target）。链接的 `target` 属性必须引用 iframe 的 `name` 属性。新链接的网页会在iframe中显示。

## HTML脚本
`<script>` 标签用于定义客户端脚本，比如 JavaScript。既可包含脚本语句，也可通过 src 属性指向外部脚本文件。
  
 `<noscript>` 标签提供无法使用脚本时的替代内容，可包含普通 HTML 页面的 body 元素中能够找到的所有元素。只有在浏览器不支持脚本或者禁用脚本时，才会起作用。

如果老式的浏览器没法识别 <script> 标签，那么 <script> 标签所包含的内容将以文本方式显示在页面上。为了避免这种情况发生，你应该将脚本隐藏在注释标签当中。那些老的浏览器将忽略这些注释，不会将标签的内容显示到页面上。而那些新的浏览器将读懂这些脚本并执行它们，即使代码被嵌套在注释标签内。
  
## HTML路径
相对路径：指向相对于当前页面的文件

绝对路径：指向一个因特网文件的完整 URL

使用相对路径是个好习惯，使用了相对路径，网页就不会与当前的基准 URL 进行绑定。所有链接在当地电脑上 (localhost) 或未来的公共域中均可正常工作。

## HTML头部
可加入的标签`<title>、<base>、<link>、<meta>、<script> 以及 <style>`

`<title>` 标签定义文档的标题

`<base> `标签为页面上的所有链接规定默认地址(URL)或默认目标（target）

`<link>` 标签定义文档与外部资源之间的关系;最常用于连接样式表

`<meta>` 标签提供关于 HTML 文档的元数据。始终位于 head 元素中, 数据不会显示在页面上，但是对于机器是可读的。
`name` 和 `content` 属性的作用是描述页面的内容，规定页面的描述、关键词、文档的作者、最后修改时间以及其他元数据。
Meta 元素中的信息可以描述 HTML 文档，可以描述文档的关键词，
在网址已经变更的情况下，将用户重定向到另外一个地址
```shell
<meta http-equiv="Refresh" content="5;url=http://www.w3school.com.cn" /> // 5 秒内被重定向到新的地址
```

## HTML实体
预留字符必须被替换为字符实体
```shell
&entity_name;
或者
&#entity_number;
```
使用实体名易于记忆，但实体数字的支持却很好。

不间断空格(&nbsp;)

**HTML实体符号参考手册：** https://www.w3school.com.cn/tags/html_ref_entities.html

## HTML统一资源定位器 URL

Uniform Resource Locator，中文也译为“统一资源定位符”，也称为网址(网页地址)

```shell
scheme://host.domain:port/path/filename
```
解释：

scheme - 定义因特网服务的类型。最常见的类型是 http

host - 定义域主机（http 的默认主机是 www）

domain - 定义因特网域名，比如 w3school.com.cn

:port - 定义主机上的端口号（http 的默认端口号是 80）

path - 定义服务器上的路径（如果省略，则文档必须位于网站的根目录中）。

filename - 定义文档/资源的名称

Web 浏览器通过 URL 从 web 服务器请求页面

URL 编码会将字符转换为可通过因特网传输的格式：1. URL 只能使用 ASCII 字符集来通过因特网进行发送；2. 使用 "%" 其后跟随两位的十六进制数来替换非 ASCII 字符；3. 不能包含空格。URL 编码通常使用 + 来替换空格


## HTML `<!DOCTYPE>` 标签
`<!DOCTYPE>` 声明必须是 HTML 文档的第一行，位于 html 标签之前。

`<!DOCTYPE>` 声明不是 HTML 标签；它是指示 web 浏览器关于页面使用哪个 HTML 版本进行编写的指令。

始终向 HTML 文档添加 !DOCTYPE 声明，这样浏览器才能获知文档类型。

在 HTML5 中只有一种声明：`<!DOCTYPE html>`

## HTML表单`<form>`
用于收集用户输入

`<input>` 元素根据不同的 type 属性，可以变化为多种形态

`<select>` 元素定义下拉列表；`<option>` 元素定义待选择的选项；与 `<input>` 元素的 list 属性引用 <datalist> 元素效果类似。

`<textarea>` 元素定义多行输入字段。单行字段定义 `<input type="text">`

`<button>` 元素定义可点击的按钮

`<datalist>` 元素为 <input> 元素规定预定义选项列表。input 元素的 list 属性必须引用 datalist 元素的 id 属性

### 输入类型`<input type="">`

文本、密码、提交、选择、按钮、数字（数字值、滑块控件）、日期、时间、颜色、邮件、搜索字段、电话号、网址、list

### 输入属性
`value` 属性规定输入字段的初始值

`name` 有此属性的输入字段才会传递到 `action` 指向的页面或程序

`readonly` 属性规定输入字段为只读（不能修改）。不需要值，它等同于 readonly="readonly"

`disabled` 属性规定输入字段是禁用的。被禁用的元素是不可用和不可点击的。被禁用的元素**不会被提交**。不需要值，它等同于 disabled="disabled"

`size` 属性规定输入字段的尺寸（以字符计）；`maxlength` 属性规定输入字段允许的最大长度

`form` 属性规定 input 元素所属的一个或多个表单。input 元素的 form 属性必须引用 所属表单 form 元素的 id 属性

```shell
<form action="action_page.php" id="form1">
   First name: <input type="text" name="fname"><br>
   <input type="submit" value="Submit">
</form>

 Last name: <input type="text" name="lname" form="form1"> //输入字段位于 HTML 表单之外（但仍属表单）
```

## HTML媒体
Web 上的多媒体指的是音效、音乐、视频和动画等。

WAVE 是因特网上最受欢迎的**无压缩**声音格式

MP4 格式是一种新的即将普及的因特网视频格式

`<object> <embed>` 用于加载插件，定义资源（通常非 HTML 资源）的容器，根据类型，它们既会由浏览器显示，也会由外部插件显示。

```shell 
// 
<object width="100%" height="100%"
type="video/x-ms-asf" url="/i/3d.wmv" data="3d.wmv"
classid="CLSID:6BF52A52-394A-11d3-B153-00C04F79FAA6">
<param name="url" value="3d.wmv">
<param name="filename" value="3d.wmv">
<param name="autostart" value="1">
<param name="uiMode" value="full" />
<param name="autosize" value="1">
<param name="playcount" value="1">                              
<embed type="application/x-mplayer2" src="/i/3d.wmv" width="100%" height="100%" autostart="true" showcontrols="true" pluginspage="http://www.microsoft.com/Windows/MediaPlayer/"></embed>
</object>
```


### 音频

`<audio> <embed>`是 HTML5 元素。

```shell
<audio controls="controls" height="100" width="100">
  <source src="song.mp3" type="audio/mp3" />
  <source src="song.ogg" type="audio/ogg" />
<embed height="100" width="100" src="song.mp3" />
</audio>
```
HTML5 audio 元素会尝试以 mp3 或 ogg 来播放音频。如果失败，代码将回退尝试 embed 元素。

向网站添加音频的最简单方法，使用雅虎播放器：

```shell
<a href="song.mp3">Play Sound</a> // 把 MP3 文件链接到 HTML 中，JS 会自动地为每首歌创建播放按钮

<script type="text/javascript" src="http://mediaplayer.yahoo.com/js"> // 插入网页底部即可
</script>
```

如果网页包含指向媒体文件的超链接，用户点击该链接，大多数浏览器会使用“辅助应用程序”来播放文件。

### 视频

最好的 HTML 视频插入解决方法：video + object + embed

```shell
<video width="320" height="240" controls="controls">
  <source src="movie.mp4" type="video/mp4" />
  <source src="movie.ogg" type="video/ogg" />
  <source src="movie.webm" type="video/webm" />
  <object data="movie.mp4" width="320" height="240">
    <embed src="movie.swf" width="320" height="240" />
  </object>
</video>
```
HTML5 video 元素会尝试播放以 mp4、ogg 或 webm 格式中的一种来播放视频。如果均失败，则回退到 embed 元素。

简单方法是 使用优酷等视频网站
```shell
<embed src="http://player.youku.com/player.php/sid/XMzI2NTc4NTMy/v.swf" 
width="480" height="400" 
type="application/x-shockwave-flash">
</embed>
```

# HTML5

## 视频

video 元素允许多个 source 元素。source 元素可以链接不同的视频文件。浏览器将使用第一个可识别的格式。video 元素开闭标签之间插入的内容是供不支持 video 元素的浏览器显示的。
```shell
<video src="movie.ogg" width="320" height="240" controls="controls">
Your browser does not support the video tag.
</video>

<video width="320" height="240" controls="controls">
  <source src="movie.ogg" type="video/ogg">
  <source src="movie.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>
```

**Video + DOM**

video 元素同样拥有方法、属性和事件；

音频 `<audio>` 使用方法基本同 video

## 拖放（Drag 和 drop）
在 HTML5 中，拖放是标准的一部分，任何元素都能够拖放s

**被拖元素** 

```shell
<img id="drag1" src="img_logo.gif" 
draggable="true" // 使元素可拖动
ondragstart="drag(event)" // 规定拖动时发生的事件，这里调用了一个函数，drag(event)，规定了被拖动的数据
width="336" height="69" />

function drag(ev)
{
ev.dataTransfer.setData("Text",ev.target.id);
}
```


