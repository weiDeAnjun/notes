# 大杂烩

 

<!--  -->		用在样式之外的地方

/**/				用在样式里

 

***\*标签语义和标签效果辩解\****

语义是语义，我要表达在这里用这个东西

![img](D:\01\技术\笔记\md文档\Web.assets\wps2433.tmp.jpg) 

标签默认的效果只是根据标签语义提供的一套默认效果  标签效果≠语义

 

 

Doctype html 不区分大小写

属性值引号可以省略，但是别这么干，多属性会出问题

字符串 单双引号包裹都可以

允许单双引号嵌套，双单引号嵌套亦可

想在字符串中表达有特殊意义的字符，可以选用实体字符

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2434.tmp.jpg) 

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2435.tmp.jpg) 

虽然对，但是尽量还是别用

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2436.tmp.jpg) 

这样不会引起误解

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2437.tmp.jpg) 

这样显示出来也只是1个空格的效果

想显示多个空格，用空格的实体字符

 

 

 

***\*插件\****

Icons

更换文件图标，通过图标传递更多信息

Auto Rename Tag

统一修改标签，省去一个个改的

会了吧

学英文的

LiveServer

写完代码，手动打开网页，要刷新网页，才能显示更新内容，在代码页面右击选择openWithLiveServer即可

而且，手动打开网页路径是文件路径，liverserver展示的路径是ip+端口号

本地打开											插件打开

![img](D:\01\技术\笔记\md文档\Web.assets\wps2438.tmp.jpg) 

 

 

# 开始

 

Web的两个功能

采集信息

展示信息

 

这两步之间的事务全部由后端处理

![img](D:\01\技术\笔记\md文档\Web.assets\wps2439.tmp.jpg) 

 

***\*客户端服务器模型\****

cs架构和bs架构

![img](D:\01\技术\笔记\md文档\Web.assets\wps243A.tmp.jpg) 

对图片补充：cs架构功能丰富，基础数据大		bs便捷

 

 

可以两个架构都有，既兼顾功能性又兼顾网页性

 

 

 

***\*浏览器内核\****

 

浏览器内核是解析前端代码的核心部分，内核不同，页面展示效果也不同

![img](D:\01\技术\笔记\md文档\Web.assets\wps243B.tmp.jpg) 

 

其它浏览器都是套壳浏览器

 

除了解析代码，还有脚本执行和资源管理两个功能

 

 

 

***\*前端三大件\****

 

Html	搭建页面架构									骨架

Css		静态样式，响应式，页面布局					血肉

Js		交互，动态效果 数据和逻辑处理 网络通信 		精神

 

***\*Emmet语法\****

它是一种快速编写 HTML 和 CSS 代码的缩写语法。它主要用于代码编辑器中，通过输入缩写形式然后扩展为完整代码结构。

 

在 HTML 中，快速生成复杂的嵌套标签

在 CSS 中可以快速生成属性和值。

 

 

***\*在 HTML 中的应用\****

标签生成

快速生成单个或多个标签。

输入div然后按下对应的扩展快捷键（在大多数编辑器中是Tab键），就会生成<div></div>。

生成多个相同的标签，例如 5 个li标签，输入li*5并按Tab键，就会生成：

<li></li>

<li></li>

<li></li>

<li></li>

<li></li>

嵌套标签生成：用于生成具有嵌套关系的标签结构。

输入ul>li*3并按Tab键，会生成一个包含 3 个li子标签的ul标签，如下所示：

<ul>

  <li></li>

  <li></li>

  <li></li>

</ul>

添加类名和 ID：可以同时为标签添加类名和 ID。

div.class1#id1会生成<div class="class1" id="id1"></div>。

还可以为多个标签添加类名，如li.item*3会生成 3 个带有item类名的li标签。

 

 

***\*在 CSS 中的应用\****

快速生成 CSS 属性和值：

输入m10（表示margin: 10px;）并按Tab键，就会生成完整的 CSS 属性。

还可以组合属性，如bd1 solid #000（表示border: 1px solid #000;）。

 

缩写选择器：对于 CSS 选择器，也有相应的缩写方式。

p+p表示相邻兄弟选择器，会生成p + p {}的 CSS 选择器代码，用于选择紧挨着的两个p标签并设置样式。

 

 

 

 

 

## HTML

告知浏览器如何组织页面的标记语言

标记语言的核心是标签，以标签实现页面效果

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps243C.tmp.jpg) 

也叫超链接

 

 

 

HTML语言发展史

![img](D:\01\技术\笔记\md文档\Web.assets\wps243D.tmp.jpg) 

在XHTML之前对语法要求宽松,标准不统一，于是标准制定者要求统一，但是程序员们觉着不好用，于是经过这么一小段支线发展后，重回HTML5

 

 

​	<body>

​		展示内容 

​	</body>

 

这段代码以html后缀打开，展示正常,以xhtml后缀打开，展示不正常

 

 

***\*Html注释\****

注释快捷键ctrl+/

 

<!--  -->

<!--  对代码进行解释说明  -->

 

<!--

允许多行

-->

 

***\*HTML文档\****

mpzilla汉化方式还原了w3c官方文档

也可以直接看w3c官方英文文档

[MDN Web Docs (mozilla.org)](https://developer.mozilla.org/zh-CN/)

 

 

行内标签不独占一行

块级标签独占一行

 

 

***\*标签+属性\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps243E.tmp.jpg) 

行内，都在1行内，所以行内元素不独占1行

块级独占1行

 

 

***\*段落\*******\*<p></p>\****

<p>段落内容</p>

<p>是块级标签



***\*强调\****

<em></em>

会变成斜体

<em>是行内标签

 

***\*<hr>\****

水平线

 

 

***\*<strong></strong>\****

加粗

 

<a>超链接文本</a>

超链接，需要配合属性才能生效

href=“”

链接文本

target = “”

![img](D:\01\技术\笔记\md文档\Web.assets\wps243F.tmp.jpg) 

_blank	新标签页

_parent	父级页面

_self	当前页面打开

_top	顶层窗口打开

在当前窗口的整个窗口中打开链接的文档。使用_target=”_top”的超链接可以覆盖所有框架和嵌套的窗口，直接在顶层窗口中加载链接的目标文档。

 

***\*标签嵌套\****

一个围堵标签内还可以写标签

 

块级标签可以嵌套块级，行内

行内标签只能嵌套行内，嵌套块级的话 行内标签的某些样式和行为可能会受到影响

![img](D:\01\技术\笔记\md文档\Web.assets\wps2440.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2441.tmp.jpg) 

 

 

***\*属性\****

属性是元素的额外信息，不会作为显示内容，但是又影响显示内容，控制标签实现不同功能，幕后的英雄

元素（包括标签），可以添加属性

 

 

布尔属性

默认一个值的属性

属性只有名，没有值，就默认true，（默认生效）

某些情况下也是属性的特殊写法和简化写法，（比如一定生效）

![img](D:\01\技术\笔记\md文档\Web.assets\wps2442.tmp.jpg)

 

***\*H\*******\*TML\*******\*结构\****

<!DOCTYPE html>			//声明当前文档类型

<html lang="zh-CN">			//整个页面的根标签

 

<head>

    <meta charset="utf=8" />	//字符集：字符和二进制的在计算机中的存储关系

<title>我的小站</title>

//页面设置，外部资源引用，标题名称设置

</head>

<body>

<p>我的页面</p>

//所有能看到的展示信息

</body>

</body>

</html>

 

<meta/>

作用：

编码集设置

<meta charset="utf=8" />

展示作者信息，别人可以用爬虫爬到

<meta name="author" content = "张三" />

meta中设置关键词，网页检索根据关键词获取信息

<meta name = "keywords" content="a,b,c" />

name设为keywords 然后content=”“，关键字以，隔开

<meta name="description" content="几乎家喻户晓"/>

配置页面描述信息，检索页面时，它会展示页面描述

 

***\*<body></body>\****

 

标题

<h1></h1>  ~  <h6></h6>

 

 

<ul>无序列表</ul>

<ul type = "circle">

​    <li>你</li>

​    <li>好</li>

​    <li>呀</li>

​    <li>朋</li>

​    <li>友</li>

  </ul>

 

<ol>有序列表</ol>

<ol type="I">

​    <li>你</li>

​    <li>好</li>

​    <li>呀</li>

​    <li>朋</li>

​    <li>友</li>

  </ol>

 

纯无序嵌套

纯有序嵌套

无序有序嵌套

 

<i></i>

单纯表达斜体效果

斜体 italic 的缩写

 

<em></em>除了能表达斜体，还能改变阅读器读音

![img](D:\01\技术\笔记\md文档\Web.assets\wps2443.tmp.jpg) 

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2444.tmp.jpg) 

 

尽量使用语义化的标签

 

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2445.tmp.jpg) 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2446.tmp.jpg) 

 

<a href="www.baidu.com">

​        <img src="C:\Users\Administrator\Desktop\Test\课外资料\KBD Life\00b9c391b17a434780aecf2b1dafd80e.jpg">

  </a>

好多东西都能当超链接

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2457.tmp.jpg) 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2458.tmp.jpg) 

 

 

 

<img>

可以选择插入本地图片和网络图片

推荐前者

后者问题多

 

 <img src="bucunzai.jpg" alt="logo" title="picture" width="" height="" align=”center”>

alt是在图片加载失败时，提示信息

![img](D:\01\技术\笔记\md文档\Web.assets\wps2459.tmp.jpg) 

title是鼠标悬停时展示内容

Width heigth 分别设置宽高，调大图片会糊，这两个属性不会手动设置，而是交给css

 

 

 

 

 

***\*表格\****

<table border="1px"  bgcolor="red" cellspacing = "0" cellpadding="3px">

  <caption>用户信息表</caption>

  <tr bgcolor = "blue"> 

​    <td>1</td>

​    <td>1</td>

​    <td>1</td>

  </tr>

  <tr>

​    <td>2</td>

​    <td>2</td>

​    <td>2</td>

  </tr>

  <tr>

​    <td>3</td>

​    <td>3</td>

​    <td>3</td>

  </tr>

 

</table>

 

border="1px" 			边框大小

cellspacing = "0"		单元格彼此间距

cellpadding="3px" 		单元格边框与内容距离

align=” ”				对齐方式

bgcolor	 		背景颜色

<caption>  </caption>	居中出现在表格上方，不会超出表格宽度

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps245A.tmp.jpg) 

 

跨列跨行操作

colspan	跨列

rowspan 跨行

![img](D:\01\技术\笔记\md文档\Web.assets\wps245B.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps245C.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps245D.tmp.jpg) 

内容不会合并

 

 

原本只有3行，跨列后变成了4行，跨会多生成一列，这会破坏整体原本的结构,应当考虑。

所以应该先删去一列再跨，才能保持原样

![img](D:\01\技术\笔记\md文档\Web.assets\wps245E.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps245F.tmp.jpg) 

 

跨行，跨行考虑列的情况，毕竟跨行实际上是合并下面行的列，
![img](D:\01\技术\笔记\md文档\Web.assets\wps2460.tmp.jpg)

 

 

表头，加粗且居中

<th></th>

<tr>

​    <th>2</th>

​    <td>2</td>

​    <td>2</td>

  </tr>

![img](D:\01\技术\笔记\md文档\Web.assets\wps2461.tmp.jpg) 

为了可读性，表格头永远要使用 ***\*<th>\**** 元素。同时切记要设置***\*cellpadding\****, ***\*cellspacing\**** 和 ***\*border\**** 的值为 ***\*0\**** ， 因为这些样式由CSS来控制更容易确保一致性。

 

 

 

***\*表单 form\****

采集信息的

![img](D:\01\技术\笔记\md文档\Web.assets\wps2462.tmp.jpg) 

[POST与GET的区别深度比较分析-阿里云开发者社区 (aliyun.com)](#:~:text=GET请求在URL中传送的参数是有长度限制的，而POST么有。,对参数的数据类型，GET只接受ASCII字符，而POST没有限制。 GET比POST更不安全，因为参数直接暴露在URL上，所以不能用来传递敏感信息。)

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2463.tmp.jpg) 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2464.tmp.jpg) 

\#提交给自己，一般用于测试

 

 

<body>

​	<form action="#" method = "get">

//表单标签，action是提交给谁，method是提交方式

​    用户名 <input type="text" name = "username">

//	input是文本域，需要指定type

​    <br><input type="submit" value="提交">

//	<br>是换行 类型：提交按钮 value：按钮上显示的内容 

​    <textarea name="text" cols="10" rows="20"></textarea>

//	文本域，cols，rows，控制文本域行列数

</form>

</body>

![img](D:\01\技术\笔记\md文档\Web.assets\wps2465.tmp.jpg) 

这是地址栏的东西，密码不能用get方式

name是给后端服务器看的，告诉服务器这个前端元素是什么

 

sex:man <input type="radio" name="sex" value="1" checked="checked">

sex:woman <input type="radio" name="sex" value="2" checked>

// 同名就会互斥

textarea同名***\*没有\****互斥，允许同名

 

checked="checked"和checked

一样的效果，标签checked默认选中

 

***\*name和value属性的区别\****

 

***\*一、\*******\*name\**** ***\*属性\****

**1.** ***\*定义\****：用于为一组相关的单选按钮（<input type="radio">）定义一个名称，以便在表单提交时能够识别这一组单选按钮。具有相同 name 值的单选按钮被视为同一组，同一组内的单选按钮在同一时间只能有一个被选中。

**2.** ***\*作用范围\****：在整个表单或特定的表单元素集合中起作用，用于区分不同的表单元素组。

**3.** ***\*示例说明\****：在多个单选按钮表示不同性别的情况下，name="sex" 定义了这一组单选按钮都与性别选择相关。当表单提交时，服务器端可以通过这个 name 值来识别用户选择的是哪一组选项中的值。

 

***\*二、\*******\*value\**** ***\*属性\****

 

**1.** ***\*定义\****：为单选按钮赋予一个特定的值，这个值在表单提交时会被发送到服务器端，用来表示用户所选择的具体选项。

**2.** ***\*作用范围\****：针对单个表单元素，为该元素定义一个提交给服务器的值。

**3.** ***\*示例说明\****：在上述例子中，value="1" 表示当这个单选按钮被选中时，提交给服务器的值为 1。通常在服务器端，可以根据这个值来判断用户选择的是男性（假设 1 代表男性）。如果还有一个单选按钮 <input type="radio" name="sex" value="2">（假设代表女性），那么根据提交的 value 值，服务器可以确定用户选择的具体性别。

 

 

***\*复选框\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps2466.tmp.jpg) 

 

 

***\*下拉菜单\****

点击后弹出下拉菜单

![img](D:\01\技术\笔记\md文档\Web.assets\wps2467.tmp.jpg) 

 

 

滚动条选择菜单	加个size属性就行

![img](D:\01\技术\笔记\md文档\Web.assets\wps2468.tmp.jpg) 

size就是菜单里展示几条，展示不了的就需要滚动查看

 

​    <select name="s1" size="1" multiple>

​      <option value="1">a</option>

​      <option value="2">b</option>

​      <option value="3">c</option>

 

​    </select>

multiple是支持多选，选定后这个菜单就可以按住ctrl多选了

 

 

***\*关于GET和POST\****

 

在 HTTP 协议中，GET 和 POST 是两种常见的请求方法，它们有以下区别：

***\*一、用途和语义\****

**·** ***\*GET\****：通常用于获取资源，例如，获取网页内容、查询数据库中的数据等，是一种幂等操作（即多次相同的请求应该产生相同的结果），不会对服务器资源产生副作用。

**·** ***\*POST\****：一般用于向服务器提交数据以进行处理，可能会对服务器资源产生影响，如创建新的资源、提交表单数据进行存储等。

***\*二、请求参数传递方式\****

**·** ***\*GET\****：请求参数附加在 URL 中，以 “?” 分隔 URL 和参数，参数之间用 “&” 连接。例如：https://example.com/search?q=keyword&page=2。这种方式使得参数在 URL 中可见，不太适合传递敏感信息，且 URL 长度有限制，通常浏览器和服务器对 URL 长度有不同的限制标准，过长的 URL 可能会导致请求失败。

**·** ***\*POST\****：请求参数放在请求体中。这种方式可以传递大量数据，并且参数对用户不可见，适合传递敏感信息。

***\*三、可缓存性\****

**·** ***\*GET\****：请求可以被缓存，除非指定了特定的缓存控制头来禁止缓存。如果响应结果是可缓存的，那么下次相同的请求可以直接从缓存中获取响应，提高性能。

**·** ***\*POST\****：默认情况下不能被缓存。因为 POST 请求通常用于修改服务器状态，缓存这样的请求可能会导致不一致的结果。

 

***\*文件域\****

用户可上传文件

![img](D:\01\技术\笔记\md文档\Web.assets\wps2469.tmp.jpg) 

要使用post提交方法，设置enctype属性

[enctype 属性规定表单数据在发送到服务器之前应如何被编码。只有在 method="post" 时才能使用。默认情况下，表单数据被编码为 "application/x-www-form-urlencoded"。](https://www.w3school.com.cn/tags/att_form_enctype.asp)

![img](D:\01\技术\笔记\md文档\Web.assets\wps246A.tmp.jpg) 

编码：空格转换为 "+" 符号，特殊字符转换为 ASCII HEX 值。[如果表单数据由多部分构成(文本、文件等二进制数据)，需要使用 multipart/form-data，才能完整的传递文件数据](https://blog.csdn.net/xuesen1995/article/details/78478179)。

 

在 HTTP 协议中，这三个是常见的请求内容类型（Content-Type），分别有以下特点：

***\*一、application/x-www-form-urlencoded\****

这是最常见的 POST 请求的内容类型。当表单以普通的 HTML 表单方式提交时，如果没有指定 enctype 属性，默认就会使用这种类型。

在这种类型下，表单数据会被编码为键值对的形式，例如 “key1=value1&key2=value2”。其中，键和值会经过 URL 编码，特殊字符会被转义成特定的格式。这种编码方式适用于简单的文本数据提交，但对于文件上传等复杂数据类型就不适用了。

***\*二、multipart/form-data\****

当需要上传文件或者提交包含非 ASCII 字符的复杂表单数据时，通常会使用这种内容类型。

在这种类型下，请求体被分割成多个部分，每个部分都有自己的头部信息，用来描述该部分的数据类型、名称等信息。例如，文件上传时，每个文件会作为一个独立的部分，并且可以包含文件名、文件类型等信息。这种方式可以有效地处理复杂的表单数据，包括文件上传和包含多种数据类型的表单提交。

***\*三、text/plain\****

表示请求体中的内容是纯文本格式。

这种内容类型通常用于简单的文本数据传输，例如发送一段日志信息或者纯文本的注释等。它不像前两种类型那样有特定的表单数据编码规则，只是简单地将文本内容作为请求体发送。一般情况下，使用这种类型的场景相对较少，因为它对于复杂数据的处理能力有限

 

 

 

***\*隐藏域\****

搜集用户不关心但服务器需要的数据

比如电子购物，用户通过输入或点击选择商品，这种数据对用户来说没有意义，但对服务方来说可以统计用户检索情况，做出商业策略调整

![img](D:\01\技术\笔记\md文档\Web.assets\wps246B.tmp.jpg) 

把隐藏域写在form里，这个form的所有提交信息会隐藏处理

 

重置按钮

![img](D:\01\技术\笔记\md文档\Web.assets\wps246C.tmp.jpg) 

普通按钮

![img](D:\01\技术\笔记\md文档\Web.assets\wps246D.tmp.jpg) 

一点都不普通，配合其它东西可以发挥出难以想象的效果

 

***\*控件禁用\****

让控件失去功能

直接添加***\*disabled\****属性就行

比如安装，已经点击安装后，软件进行安装，这时候安装按钮就是失效，防止反复装

 

 

***\*回显\****

回显就是控件禁用后，显示内容

![img](D:\01\技术\笔记\md文档\Web.assets\wps246E.tmp.jpg) 

一般表示用户输入信息后，该信息不可再修改

或者锁定信息只能是xxx

***\*题外话\****

这个信息是Value

Value对按钮和数据域（如文本域，密码域）来说不一样

按钮的value代表该按钮的值，提交使用

数据域的value代表在数据域的框框上显示该value数值

题外话结束

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps246F.tmp.jpg) 

禁用的控件携带的数据不会上传

因为传上来服务器也不会修改

不修改，就没意义了

 

***\*L\*******\*abel\****

增强可访问性

 

提高屏幕阅读器的可用性：对于视力障碍用户使用的屏幕阅读器软件，<label>标签可以明确地将表单元素与一个文本标签关联起来。当用户通过屏幕阅读器浏览网页时，软件可以准确地读出每个表单元素的标签文本，让用户清楚地知道该输入框或选择框的用途。

比如这个：![img](D:\01\技术\笔记\md文档\Web.assets\wps2470.tmp.jpg)

我点表单元素，会有输入效果，我点文字标签，也有这个效果，对特殊人群来说，体验友好

label前：

![img](D:\01\技术\笔记\md文档\Web.assets\wps2471.tmp.jpg) 

label后：

![img](D:\01\技术\笔记\md文档\Web.assets\wps2472.tmp.jpg) 

 

方便键盘操作：当用户使用键盘在表单中导航时，点击 <label> 标签可以自动将焦点切换到对应的表单元素上。例如，对于一个文本输入框，如果有一个 <label> 标签与其关联，用户按下键盘上的 Tab 键导航到该标签时，再按下空格键就可以将焦点转移到对应的输入框，方便用户快速定位和操作表单元素。

扩大可点击区域：<label>标签的点击区域通常比表单元素本身要大，这使得用户在点击操作时更加容易准确地选中目标表单元素。特别是在移动设备上，用户的手指操作相对不够精准，较大的点击区域可以提高用户操作的成功率和便利性。

 

也可以将表单元素直接放在 <label> 标签内部，实现隐式关联。例如，<label>用户名：<input type="text"></label>。这种方式更加简洁直观，但需要注意的是，不同的浏览器可能对这种方式的支持程度略有差异。

  <label>用户名：<input type="text"></label>

 

 

新技术
解决了问题，更高效，可读性好

 

 

 

 

## CSS样式控制/层叠样式表

设定样式 -> 展示效果

样式和内容无关

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2483.tmp.jpg)
div和span是两个非语义化标签，两张白纸  可用css随意书写样式

div	块级

span行级

 

 

 

css相关内容写在<head></head>中

<head>

    <style>

​    .c1{

​      color: #0ffacd;

​      border: #ffffff;

​      font-family: sans-serif;

​    }

  </style>

</head>

<body>

    <table class="c1">

  </table>

</body>

 

 

 

 

css选择器类型：

标签选择器	类选择器		ID选择器	全局选择器	属性选择器	子字符串匹配选择器	伪类选择器

交集/并集选择器	

 

***\*标签选择器\****

给这类标签设定样式，只要是这种标签就自动使用这种样式

![img](D:\01\技术\笔记\md文档\Web.assets\wps2484.tmp.jpg) 

 

 

***\*类选择器\****
 ***\*.\**** 开头，标签元素以属性class = ” ” 引用

![img](D:\01\技术\笔记\md文档\Web.assets\wps2485.tmp.jpg)![img](D:\01\技术\笔记\md文档\Web.assets\wps2486.tmp.jpg) 

 

***\*ID选择器\****

\#开头，具有该ID的标签元素自动使用

![img](D:\01\技术\笔记\md文档\Web.assets\wps2487.tmp.jpg)![img](D:\01\技术\笔记\md文档\Web.assets\wps2488.tmp.jpg) 

 

***\*全局选择器\****

仅一个 *  ，所有标签元素都会用它的样式

![img](D:\01\技术\笔记\md文档\Web.assets\wps2489.tmp.jpg) 

 

 

***\*属性选择器\****

根据属性、属性值匹配，作用于标签元素

属性选择器是一类：

根据属性名
![img](D:\01\技术\笔记\md文档\Web.assets\wps248A.tmp.jpg)

包含属性class的标签使用样式

根据属性名+属性值

![img](D:\01\技术\笔记\md文档\Web.assets\wps248B.tmp.jpg) 

包含属性class且class值***\*仅包含\****a的标签使用样式
如果包含属性class且class值为a的同时，***\*还包含其他值\****，就***\*不生效\*******\*
\****![img](D:\01\技术\笔记\md文档\Web.assets\wps248C.tmp.jpg)
34均不生效


包含属性class且class值***\*只要包含\****a的标签使用样式
![img](D:\01\技术\笔记\md文档\Web.assets\wps248D.tmp.jpg)
![img](D:\01\技术\笔记\md文档\Web.assets\wps248E.tmp.jpg)
3生效
4不生效， 因为内容没以 ***\*空格\**** 分开
想让4生效，可以用子字符串匹配选择器（下面说)

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps248F.tmp.jpg)
以top开头且紧跟-

就是top-开头的内容，后面跟什么都无所谓，都能匹配上

![img](D:\01\技术\笔记\md文档\Web.assets\wps2490.tmp.jpg) 

5生效
6不生效

 

格式：
	标签名[标签属性]
	标签名[标签属性=””]
	标签名[标签属性~=””]
	标签名[标签属性|=””]

 

 

***\*子字符串匹配选择器\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps2491.tmp.jpg) 

匹配任何包含class（这个下文不再提及）

匹配以a开头的属性

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2492.tmp.jpg)
匹配以a结尾的属性

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2493.tmp.jpg)
匹配出现a的属性

 

如果想忽略大小写匹配
![img](D:\01\技术\笔记\md文档\Web.assets\wps2494.tmp.jpg)
i是大小写敏感忽略标记

 

格式

​	标签名[标签属性^=””]			匹配开头

​	标签名[标签属性$=””]			匹配结尾

​	标签名[标签属性*=””]			任意匹配

​	标签名[标签属性=”” 空格i]		忽略大小写

 



***\*伪类选择器\****

伪类选择器的作用目的一般都非常明显

 

说伪类选择器，就要通过类选择器辨别性认识它：

类选择器有个特点，所有使用该 类选择器 的标签元素可以看作是一类，这个类是使用者手动划分的

伪类选择器也有这个特点，不过它是自动分类：元素如果符合了该伪类选择器要求的条件，就会使用它的样式。

 

伪类选择器也是一类选择器：

***\*普通伪类选择器\****

***\*符合什么条件\****，比如是第一个元素，是大小16px的元素，是div标签元素等

***\*行为伪类选择器\****

有什么动作，比如被点击，被松开点击等

 

***\*区分二者的关键在于  是否\*******\*涉及用户的交互行为\****

 

例如

普通：

link选择未被访问过的链接，:visited选择已被访问过的链接，:hover选择鼠标悬停在其上的元素，:active选择被激活（如正在被点击）的元素，:first-child选择父元素的第一个子元素，:nth-child(n)选择父元素的第 n 个子元素等。

这些伪类选择器主要是基于元素的静态特征或在不同状态下的表现来进行选择，不依赖于用户的具体操作行为。

 

行为：

用户通过键盘或鼠标操作使元素获得焦点，如输入框在被点击或通过键盘导航选中时。

用户点击一个锚点链接时，对应的目标元素会被:target选择器选中。

 

 

 

伪类选择器可以***\*作用于任何 HTML 元素\****，包括标签、类选择器、ID 选择器等 所选中的元素。

格式：

被作用对象：伪类选择器{

}

 

普通伪类选择器

/* 作用于所有 a 标签且为未访问状态的链接 */

a:link {

 color: blue;}

/* 作用于具有特定类名的元素，当鼠标悬停时 */

.my-class:hover {

 background-color: yellow;}

/* 作用于 ID 为 my-id 的元素的第一个子元素 */

\#my-id > :first-child {

 font-weight: bold;}

 

 

 

 

行为伪类选择器

![img](D:\01\技术\笔记\md文档\Web.assets\wps2495.tmp.jpg) 

 

 

 

 

伪类选择器有很多现成的

![img](D:\01\技术\笔记\md文档\Web.assets\wps2496.tmp.jpg) 

 

 

选择器优先级?
选择器可以作用在选择器上吗？

视频提及的网站

 

 

 

## JS

 

JavaScript 与 Java 是两种完全不同的语言，无论在概念上还是设计上。只是名字像。
ECMA-262 是 JavaScript 标准的官方名称。


JavaScript是***\*脚本语言\*******\*
\****	脚本是使用特定的语言依据一定格式编写的可执行文件，又称作宏或批处理文件。

脚本（Script）的意思最早是从演艺界来的，即按照脚本表演，没有脚本就即兴发挥。

 

脚本带来的最大变化是一个规程可以不断重复。

 

脚本的用意是为了可再现的重复一个设定好的规程。

脚本需要有一个解释器来执行。

脚本能够方便的，快速的，经常的被修改。

所以说，要是打比喻：

你打开资源管理器，用鼠标把一个文件拖到另外一个地方，这是即兴表演。

你写几行命令，把他保存下来， 一执行就做了上面的事情，这就是脚本。

![img](D:\01\技术\笔记\md文档\Web.assets\wps2497.tmp.jpg) 

 

 

***\*用js可以\****
写入html输出流
对事件反应
改变html内容
使前端具有	逻辑处理、验证信息	功能

​	***\*以<script></script>包围\****

可以写在头或身体标签里

 


	举例
document.write( )

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2498.tmp.jpg) 

只能在 HTML ***\*输出流\****中使用document.write()。 文档已加载后使用它（比如在函数中），会覆盖整个文档。


所谓的输出流，就是HTML渲染页面 到 实现输出的过程。HTML的加载过程是由上至下的，当遇到js脚本时，页面加载会被阻塞，浏览器会先去下载js脚本，当js脚本运行完之后，再继续渲染页面。

而当页面已经加载完成后，再通过js写入HTML输出流时，页面会重新加载，此时之前已经加载的东西会全部消失，只加载js中的内容。


Javascript 脚本代码必须位于 <script> 与 </script> 标签之间。
Javascript 脚本代码可被放置在 HTML 页面的 <body> 和 <head> 部分中。
通常的做法是把函数放入 <head> 部分中，或者放在页面底部。这样就可以把它们安置到同一处位置，不会干扰页面的内容。



通常，我们需要在某个事件发生时执行代码，比如当用户点击按钮时。
如果我们把 JavaScript 代码放入函数中，就可以在事件发生时调用该函数。
就是事件触发函数，函数里有js，所以执行改js

​	
​	***\*外部js\****

也可以把脚本保存到外部文件中。外部文件通常包含被多个网页使用的代码。
外部 JavaScript 文件的文件***\*扩展名 .js\****
外部 javascript 文件不使用 <script> 标签，直接写 javascript 代码。
	

引用例子
<script src="myScript.js"></script>
在script中用src引用



HTML 输出流中使用 document.write，相当于添加在原有html代码中添加一串html代码。而如果在文档加载后使用（***\*如使用函数\****），会覆盖整个文档。

使用函数来执行document.write代码如下：

<script>

  function myfunction(){

  document.write("使用函数来执行document.write，即在文档加载后再执行这个操作，会实现文档覆盖");}

  document.write("<h1>这是一个标题</h1>");

 document.write("<p>这是一个段落。</p>");

</script>

<p>

您只能在 HTML 输出流中使用 <strong>document.write</strong>。

如果您在文档已加载后使用它（比如在函数中），会覆盖整个文档。

</p>

<button type="button" onclick="myfunction()">点击这里</button>

 

 

引入文件和本地文件没有优先级，就是依照从上到下执行

 

 


	***\*js输出\****
JavaScript 没有任何打印或者输出的函数。
但可以通过不同的方式来输出数据：
使用 window.alert() 弹出警告框。
使用 document.write() 方法将内容写到 HTML 文档中。
使用 innerHTML 写入到 HTML 元素。
使用 console.log() 写入到浏览器的控制台。

浏览器控制台是什么？

 

例：
<script>
window.alert(5 + 6);		//弹出11
</script>


	***\*访问html元\*******\*素\****
如需从 JavaScript 访问某个 HTML 元素，您可以使用 document.getElementById(id) 方法。
并 innerHTML 来获取或插入元素内容
只能通过id

例子
<script>											
document.getElementById("demo").innerHTML = "段落已修改。";
</script>														





***\*写到控制台\****

向控制台写入数据

一般用来调试

使用 console.log() 方法在浏览器中显示 JavaScript 值。

 

浏览器中使用 F12 来启用调试模式， 在调试窗口中点击 "Console" 菜单。

![img](D:\01\技术\笔记\md文档\Web.assets\wps2499.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps249A.tmp.jpg) 

***\*一些对比\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps249B.tmp.jpg) 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps249C.tmp.jpg) 

页面载入过程中用实时脚本创建页面内容，用来追加一些标签。

 

document.write加载后覆盖页面的问题可以解决

![img](D:\01\技术\笔记\md文档\Web.assets\wps249D.tmp.jpg) 

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps249E.tmp.jpg) 

 

 

***\*Js变量\****

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps249F.tmp.jpg) 

 

***\*js字面量\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps24A0.tmp.jpg) 

我的一些疑问：数组、对象不需要名字？允许不同类型吗？允许嵌套吗？

 

 

16 + "Volvo" =  “16Volvo”

 



***\*var变量\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps24A1.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24A2.tmp.jpg) 

var可以接收任意类型变量，但不代表变量只有var类型

 

 

 

 

***\*number类型\****

整型、浮点型、±无穷大、NaN

 

±无穷大

![img](D:\01\技术\笔记\md文档\Web.assets\wps24B2.tmp.jpg)![img](D:\01\技术\笔记\md文档\Web.assets\wps24B3.tmp.jpg)![img](D:\01\技术\笔记\md文档\Web.assets\wps24B4.tmp.jpg) 

Js中不报错，会把这种情况视作无穷大

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24B5.tmp.jpg) 

转换为number类型，111a以数字开头，所以可以转成且结果为111

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24B6.tmp.jpg) 

转换为number类型，a111以字母开头，所以结果为NaN，但类型依然转换成功了，现在a111是number类型

![img](D:\01\技术\笔记\md文档\Web.assets\wps24B7.tmp.jpg) 

 

↑

Js转为number类型，数字和非数字类型混合，无论谁开头，都转为number类型，若数字开头，仅保留 首个连续数字部分，否则为NaN

 

 

 

 ***\*boolean类型\****

 

 

 

***\*undefined类型\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps24B8.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24B9.tmp.jpg) 

 

***\*String类型\****

 

单双引号都表示string类型

 

 

 

***\*none类型\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps24BA.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24BB.tmp.jpg) 

null是object类型

 

 

***\*强制类型转换\****

 

***\*字符串转number类型\****		***\*Number（“”）\****

 

它比如parseInt、parseFloat更严格，数字非数组混合会判定为NaN

 

 

***\*转Boolean类型\****	***\*Boolean（）\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps24BC.tmp.jpg) 

 

 

***\*转String\****		***\*String()\****

 

 

 

***\*parseInt() parseFloat()\****

 

Number()严格，它俩宽松

 

 

 

 

***\*Js运算符\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps24BD.tmp.jpg) 

 / 得到Float类型

 

 

 

其它按java规则来

 

 

 

 

***\*隐式转换\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps24BE.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24BF.tmp.jpg) 

 	

 

 

 

 

***\*Js保留关键字\****

| abstract | else       | instanceof | super        |
| -------- | ---------- | ---------- | ------------ |
|          |            |            |              |
| boolean  | enum       | int        | switch       |
|          |            |            |              |
| break    | export     | interface  | synchronized |
|          |            |            |              |
| byte     | extends    | let        | this         |
|          |            |            |              |
| case     | false      | long       | throw        |
|          |            |            |              |
| catch    | final      | native     | throws       |
|          |            |            |              |
| char     | finally    | new        | transient    |
|          |            |            |              |
| class    | float      | null       | true         |
|          |            |            |              |
| const    | for        | package    | try          |
|          |            |            |              |
| continue | function   | private    | typeof       |
|          |            |            |              |
| debugger | goto       | protected  | var          |
|          |            |            |              |
| default  | if         | public     | void         |
|          |            |            |              |
| delete   | implements | return     | volatile     |
|          |            |            |              |
| do       | import     | short      | while        |
|          |            |            |              |
| double   | in         | static     | with         |

 

 

有个情况需要特别注意: typeof 不能用来判断是 Array 还是Object

var arr = [] typeof(arr) === 'object' // true

结果为 true。

当然你可以使用其他方式来判断：

 

1、使用 isArray 方法

var cars=new Array();

cars[0]="Saab";

cars[1]="Volvo";

cars[2]="BMW";// 判断是否支持该方法if (Array.isArray) {

  if(Array.isArray(cars)) {

​    document.write("该对象是一个数组。") ;

  }}

2、使用 instanceof 操作符

var cars=new Array();

cars[0]="Saab";

cars[1]="Volvo";

cars[2]="BMW";

if (cars instanceof Array) {

  document.write("该对象是一个数组。") ;}

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24C0.tmp.jpg) 

 

 

 

***\*JavaScript 代码块\****

JavaScript 可以分批地组合起来。

代码块以左花括号开始，以右花括号结束。

代码块的作用是一并地执行语句序列。

![img](D:\01\技术\笔记\md文档\Web.assets\wps24C1.tmp.jpg) 

 

可以在文本字符串中使用反斜杠对代码行进行换行。

![img](D:\01\技术\笔记\md文档\Web.assets\wps24C2.tmp.jpg) 

 

***\*js变量命名\****

变量必须以字母开头

变量也能以 $ 和 _ 符号开头（不过我们不推荐这么做）

大小写敏感

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24C3.tmp.jpg) 

就是第二句不报错

就好像说话说了一半，说了，但又什么都没说，就当你在放屁

 

 

JavaScript 允许变量被重复声明，在声明变量时 JavaScript 会自行判断这个变量是否已经被声明了，如果已经被声明（即已经存在），那么重复声明（即除了变量的非首次声明）会被跳过，不再执行声明的操作。

 

JavaScript 变量的值是可以被重复赋值的，最后的赋值是这个变量最后的结果。

 

var a = 1;var a = 'x';

console.log(a);// 输出 'x'

 

 

 

 

const 关键字定义常量

let 关键字定义限定作用域的变量

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24C4.tmp.jpg) 

 

 

***\*Js函数\****

 

***\*函数\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps24D5.tmp.jpg) 

***\*函数表达式\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps24D6.tmp.jpg) 

 

***\*函数arguments对象\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps24D7.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24D8.tmp.jpg) 

***\*返回1个对象\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps24D9.tmp.jpg) 

 

 

 

***\*除了变量，\*******\*JavaScript\**** ***\*也\*******\*允许重复定义函数\****

 

JavaScript 没有重载这个概念，它仅依据函数名来区分函数

 

后定义的同名函数覆盖之前的，与参数无关。

 

 

function test() {

  console.log("test");}

test();   //输出 "test arg0 + undefined"

function test(arg1) {

  console.log("test arg" + arguments.length + " + " + arg1);}

test(1,2);  //输出 "test arg2 + 1"

 

 

实参个数如果比形参少，那么剩下的默认赋值为 ***\*undefined\****，如果实参传的比形参数量多，那么是全部都会被传进去的，只不过没有对应的形参可以引用（但可以用 arguments 来获取剩下的参数）。

 

 

function test(arg1) {

  for(var i=0; i<arguments.length; i++) {

​    console.log(arguments[i]);

  }}

test(1,2); //输出 1 2

 

 

***\*变量与函数重名的时候，变量生效\****

 

这涉及到了变量和函数的预解析：

变量声明会被顶置，函数声明也会被顶置 且 比变量更先声明

变量的声明和赋值语句一起写时，JS引擎在解析时，会将其拆成声明和赋值2部分，声明置顶，赋值保留在原来位置。

声明过的变量不会再重复声明

var a = 100;

function a() {

​	return "function";

}

console.log(a);   //输出 100

console.log(a());  /*

报错

Uncaught TypeError: a is not a function

  (anonymous function) @test.html:9

*/

JS 中有两种函数，一种是普通函数，一种是函数对象。下面的这种就是“函数对象”，它实际上是声明一个匿名函数，然后将该函数的 init 方法赋值给该变量。

var a = 100;

var a = function() {

  return "function";

}

console.log(a);/* 

输出

function() {

  return "function";

}

*/

console.log(a());  //输出 "function"

 

***\*函数与内部变量重名\****

定义普通函数，即在 window 变量下，定义一个 key，它的名字为该函数名，值为该函数的地址。函数内部的 this 指向 window 对象。

function a() {

  console.log(this);  //输出 window{...}

  this.a = 1;     //即 window.a = 1，此时window下的function a已经被该变量覆盖了。

  var a = 5;      //下面的这几个变量都是局部变量，仅在花括号范围内有效。  

  a = 10;

  var v = "value"

  return "function";}

console.log(a);     //输出 function a {...}

console.log(a());    //输出 "function"

console.log(a);     //输出 1

console.log(v);/*

输出

Uncaught ReferenceError: v is not defined

  (anonymous function) @ mycolor.html:15

*/

 

var a=1;var a=2;

//赋值覆盖相当于：var a;//a=1;

a=2;

//声明覆盖相当于：//var a=1;var a=2;

1. 

这个笔记所说的覆盖，其实是赋值的覆盖。如果说后声明的会覆盖已声明的，那么后声明的应该是 undefined 而不是第一次声明时候的赋值，也就是说如果是声明覆盖的话，相当于没有 var a=1 那么一个只有声明没有赋值的变量，它的值就是 undefined。

2. 

我们如何验证这个覆盖是声明的覆盖还是赋值的覆盖呢？看下面的代码：

3. 

var a=1;var a;

//赋值覆盖相当于：var a;//a=1;

a;

//声明覆盖相当于：//var a=1;var a;

4. 

我们再输出a的值，验证下是 undefined 还是 1 就知道了。

5. 

console.log(a);

 

***\*同名声明赋值的变量：\****逐条进行-后者覆盖前者。（同级别覆盖）

6. 

var a = 1; var a = 2;

console.log(a); // 输出结果：2

7. 

***\*同名声明赋值的-函数和变量：\****逐条进行-后者覆盖前者。（同级别覆盖）

8. 

var a = 1; var a = function () {   }

console.log(a); //输出结果： a 函数

9. 

\-----------------------------------------------------------------

10. 

***\*注：\*******\*var f = function () {}\**** 和 ***\*function f () {}\**** 的区别（有var就有内存）

11. 

var f = function () {console.log("有var")} // 声明函数function f () {} // 未声明函数

console.log(f); // 输出结果： 有var的f函数

12. 

\-----------------------------------------------------------------

13. 

***\*同名声明的变量：\****赋值的级别高。（同名声明未赋值）

14. 

var a = 1; // 赋值var a; // 未赋值

console.log(a); // 输出结果： 1

15. 

\-----------------------------------------------------------------

16. 

***\*声明和未声明的同名变量：\****后者是重新赋值。（同名未声明赋值）

17. 

var a = 1; // 声明赋值

a =2 ; // 未声明变量

console.log(a);   // 输出结果： 2 var f = function () {} // 声明赋值

f = function () {console.log("赋值")} // 未声明变量

console.log(f);  // 输出结果：function () {console.log("赋值")}

18. 

 

 

 

***\*js数组\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps24DA.tmp.jpg) 

 

 

***\*js对象\****

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24DB.tmp.jpg) 

可以发现参数是 即时 定义的，直接.都能造出来

通过这个特性，直接在函数里造

![img](D:\01\技术\笔记\md文档\Web.assets\wps24DC.tmp.jpg) 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24DD.tmp.jpg) 

.	或	[]	的方式寻址，一种像类，一种像数组下标

 

 

***\*对象方法\****

就是对象的属性是方法（函数），这个函数叫对象方法。

 

使用以下语法创建对象方法：

fullName : function() {

// 代码

}

 

var person = {

  firstName: "John",

  lastName : "Doe",

  id : 5566,

  fullName : function() 

​	{

​    return this.firstName + " " + this.lastName;

  }

};

 

 

要注意fullName 和fullName() 都能用

![img](D:\01\技术\笔记\md文档\Web.assets\wps24DE.tmp.jpg) 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24DF.tmp.jpg) 

 

 

javaScript对象中属性具有唯一性（这里的属性包括方法），如果有两个重复的属性，则以最后赋值为准。

 

 

键的类型是字符串或符号，一般类型都是转换成字符串（对象数字等类型），但是符号不会被强制转换。

注意：如果把符号用作对象的属性 / 键值，那么它会以一种特殊的方式存储，使得这个属性不出现在枚举中，要通过原型链上的函数 .getOwnPropertySymbols 才能找到：

![img](D:\01\技术\笔记\md文档\Web.assets\wps24E0.tmp.jpg) 

 

 

 

一般情况下 [] 适用于任何形式的取值，但是 . 并不一定适用于所有的情况，下边介绍两种情况的区别。

1、当所取的属性名是一个动态的值时，只能用[]不能用。

 2、当所取得键名是一个特殊的字符串时，只能用[]不能用。

什么是特殊：当键名试一下情况下，键名是一个含有数字的字符串；当键名有特殊符号时；当键值是一个引号引起来的字符串时。

所以尽量用 [ ]

let person = {

  name : '饺子',

  age : 18,

  //以下属加引号是为了将其视为整体，两种访问方式区别情况2也体现在这

  "123":"chinese", 

  "my-job" : "我的工作，中间是连字符",

  "my word" : "我的，中间含有一个空格",

  say(){

​    console.log(this.name+"年龄是:" + this.age);

  } };

// 两种方式都可以访问属性和方法

console.log(person.name) 

console.log(person.age)

person.say()

 

console.log(person["name"])

console.log(person["age"])

person["say"]()

// 区别1：动态变量作为属性// 这里定义一个myName,值为对象属性中的一个键名，在这里是直接定义的，但是在开发环境中可能是接手的其他的可变化的值let myName = "name"

console.log(person.myName)     // undefined，使用.访问，不会取出myName的值，会在person对象上查找键名为"myName"的属性值，因为没有所以肯定也找不到了

console.log(person[myName])     // zhangsan，使用[]访问，中括号访问会把动态变量转换为实际的变量,这里就相当于person[name]

//区别2：特殊字符//console.log(person.123)     // 报错//console.log(person.my-job)   // 报错//console.log(person.my word)   // 报错

console.log(person[123])     // undefined

console.log(person["123"])     // chinese，注意只有合理的数字才能省略引号

console.log(person["my-job"])  // 我的工作，中间是连字符

console.log(person["my word"])  // 我的，中间含有一个空格

 

声明函数时，请把参数作为变量来声明：

function myFunction(var1,var2)
{
代码
}

 

只要在函数外声明的变量就是全局变量，网页上的所有脚本和函数都能访问它。

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24E1.tmp.jpg) 

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24E2.tmp.jpg) 

 

 

***\*js事件\****

[HTML DOM 事件对象 | 菜鸟教程](https://www.runoob.com/jsref/dom-obj-event.html)

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24E3.tmp.jpg) 

 

 

应该还有很多事件相关的知识才对

 

 

 

 

 

 

***\*js字符串\****

 

可以使用索引位置来访问字符串中的每个字符

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24E4.tmp.jpg) 

 

可以使用内置属性 ***\*length\**** 来计算字符串的长度

 

 

=== 为绝对相等，即数据类型与值都必须相等。

不同类型间比较，== 比较会 "转化成同一类型后的值" 看 "值" 是否相等

 

对于 Array,Object 等高级类型，== 和 === 是没有区别的

进行 "指针地址" 比较

基础类型与高级类型，== 和 === 是有区别的

对于 ==，将高级转化为基础类型，进行 "值" 比较

因为类型不同，=== 结果为 false

!= 为 == 的非运算， !== 为 === 的非运算

 

 

原始值字符串，如 "John", 没有属性和方法(因为他们不是对象)。

原始值可以使用 JavaScript 的属性和方法，因为 JavaScript 在执行方法和属性时可以把原始值当作对象。

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24E5.tmp.jpg) 

 

字符串方法

[JavaScript String 对象 | 菜鸟教程](https://www.runoob.com/jsref/jsref-obj-string.html)

 

 

 

***\*js模板字符串\****

 

可以嵌入表达式和变量的字符串

``	包裹嵌入内容（专业术语定界符）

![img](D:\01\技术\笔记\md文档\Web.assets\wps24F6.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24F7.tmp.jpg) 

${expression}	占位符	引用变量、执行函数调用和进行任意的JavaScript表达式

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24F8.tmp.jpg) 

 

 

***\*js正则表达式\****

定义了字符串组成的规则

 

2种定义方式

![img](D:\01\技术\笔记\md文档\Web.assets\wps24F9.tmp.jpg) 

 

使用RegExp的test（）方法进行验证

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24FA.tmp.jpg) 

 

 

***\*Js对象\****

 

自定义对象

![img](D:\01\技术\笔记\md文档\Web.assets\wps24FB.tmp.jpg) 

在自定义对象中使用自定义对象中定义的内容，必须以	this.		的形式，否则提示未定义

原因：

作用域链

JavaScript 的作用域链是基于函数的。当在一个函数内部访问一个变量时，JavaScript 引擎会首先在当前函数的作用域内查找，如果找不到，就会沿着作用域链向上查找，直到找到全局作用域。但是，对于对象的属性和方法，它们并不直接处于函数的作用域链上。

变量提升与函数提升

在 JavaScript 中，变量声明会被提升到函数作用域的顶部，但变量的赋值不会被提升。而函数声明会被整体提升到作用域的顶部。然而，对象的属性和方法并不遵循这种提升规则。它们只有在对象被创建并且属性和方法被添加到对象上之后才存在。

 

 

***\*js运算符\****

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24FC.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24FD.tmp.jpg) 

如需把两个或多个字符串变量连接起来，请使用 ***\*+\**** 运算符。

数字与字符串相加，返回字符串

![img](D:\01\技术\笔记\md文档\Web.assets\wps24FE.tmp.jpg) 

原因就是在字符串运算没出现之前，按照数字运算来

数字和布尔值相加，布尔值转数字， false 转成 0，true 转成 1

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps24FF.tmp.jpg) 

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2500.tmp.jpg) 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2501.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2502.tmp.jpg) 

 

 

其他数据类型转换为布尔类型的规则: null、undefined、0、NaN、空字符串转换为false，其他转化为 true。

 

var a = [1,2,3];var b = "hello";var obj = new Object();var d;

 

console.log(!"");  //true

console.log(!d);   //true

console.log(!a);   //false

console.log(!b);   //false

console.log(!obj);  //false

 

 

 

 

 

如果要把字符串转换为数字，可以通过减 - 运算来进行，当然这里有一种情况，就是参与运算的 string 不能被转换成合法的 number 类型，那么最后结果就会返回 NaN。

 

var x='1';

console.log(typeof x);

x=x-0;

console.log(typeof x);

var y='2';

y=y-1;

console.log(y);var z='abc';

z=z-2;

console.log(z);

 

 

Js也有三目

 

let age = 18;

let message = age >= 18? "成年人" : "未成年人";

console.log(message); // 输出：成年人

 

 

***\*BOM\****

浏览器对象模型

浏览器看作对象，它由很多子模块组成

 

Js将浏览器的各个子模块部分封装成对象，可以方便的操作这些子模块

![img](D:\01\技术\笔记\md文档\Web.assets\wps2503.tmp.jpg) 

 

 

***\*windows主要方法\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps2504.tmp.jpg) 

 

 

***\*history主要方法\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps2505.tmp.jpg) 

 

 

location

![img](D:\01\技术\笔记\md文档\Web.assets\wps2506.tmp.jpg) 

 

 

 

 

 

***\*DOM\****

 文档对象模型

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2507.tmp.jpg) 

 

DOM把标签封装为对象

它将 HTML 或 XML 文档表示为一棵树状结构。

这棵树的每一个节点都代表了文档中的一个元素、属性或文本。

然后就可以通过Js操作这棵树

Js提供丰富的API操作DOM

 

选择元素：

 

document.getElementById('id'): 通过 ID 选择元素。

document.querySelector('selector'): 通过 CSS 选择器选择第一个匹配的元素。

document.querySelectorAll('selector'): 通过 CSS 选择器选择所有匹配的元素。

document.getElementsByClassName('className'): 通过类名选择元素。

document.getElementsByTagName('tagName'): 通过标签名选择元素。

 

修改元素内容：

element.innerHTML = 'new content': 修改元素的 HTML 内容。

element.textContent = 'new text': 修改元素的文本内容。

element.setAttribute('attribute', 'value'): 设置元素的属性。

 

修改元素样式：

element.style.property = 'value': 修改元素的 CSS 样式。

element.classList.add('className'): 添加类名。

element.classList.remove('className'): 移除类名。

 

创建和插入元素：

document.createElement('tagName'): 创建新的元素。

element.appendChild(newElement): 将新的元素添加到现有元素的末尾。

element.insertBefore(newElement, referenceElement): 将新的元素插入到现有元素之前。

 

事件监听：

element.addEventListener('event', function): 监听元素的事件，并在事件发生时执行指定的函数。

 

 

原文链接：https://blog.csdn.net/q68686/article/details/144978500

 

所有标签父对象都是Element

 

 

 

***\*Js内置对象\****

好像java中的类

***\*数组\****

Js中数组 存储多种类型，长度动态调整，是弱类型

![img](D:\01\技术\笔记\md文档\Web.assets\wps2508.tmp.jpg) 

 

若数组10个元素，但改变它length为5，则数组将只保留前5个元素。

Js中数组length属性可随时调整，并影响数组元素

 

***\*数学对象Math\****

 

Math.

 

***\*日期对象Date\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps2509.tmp.jpg) 

月份0~11，像数组下标一样

 

 也可以用毫秒值表示日期

![img](D:\01\技术\笔记\md文档\Web.assets\wps250B.tmp.jpg) 

 

传入代表时间的字符串也行

![img](D:\01\技术\笔记\md文档\Web.assets\wps250C.tmp.jpg) 

 

 

***\*正则对象\****

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps250D.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps250E.tmp.jpg) 

 

 

***\*警告、询问、确认 框\****

不用windows.调用也行

windows.alert();

windows.prompt();

windows.confirm();

 

***\*定时器\****

单位毫秒

重复执行的定时器

![img](D:\01\技术\笔记\md文档\Web.assets\wps250F.tmp.jpg) 

一次性定时器

![img](D:\01\技术\笔记\md文档\Web.assets\wps2510.tmp.jpg) 

 

 ***\*自定义对象\****

***\*定义方式1：\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps2511.tmp.jpg) 

和java类定义不同，Js直接 定义 和 实例化 一体

注意用this访问自定义对象属性

***\*定义方式2：\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps2512.tmp.jpg) 

注意show

 

***\*Document对象\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps2521.tmp.jpg) 

从文档(网页源码？)中获取内容，script标签需要写在body标签最下面，因为body要在script之前加载才能读取到

 

document.xxx![img](D:\01\技术\笔记\md文档\Web.assets\wps2522.tmp.jpg)

![img](D:\01\技术\笔记\md文档\Web.assets\wps2523.tmp.jpg) 

 

 

***\*element元素\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps2524.tmp.jpg) 

 

***\*插入节点\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps2525.tmp.jpg) 

指定位置插入

![img](D:\01\技术\笔记\md文档\Web.assets\wps2526.tmp.jpg) 

在p前插入title

***\*删除节点\****

删除节点需要获得父节点

![img](D:\01\技术\笔记\md文档\Web.assets\wps2527.tmp.jpg) 

 

***\*表单操作\****

 

 

***\*事件\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps2528.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2529.tmp.jpg) 

 

单击事件

![img](D:\01\技术\笔记\md文档\Web.assets\wps252A.tmp.jpg) 

 

焦点事件

 

 

页面加载

![img](D:\01\技术\笔记\md文档\Web.assets\wps252B.tmp.jpg) 

虽然放在body前，但页面加载完成后它才生效

 

***\*BOM对象\****

location跳转

![img](D:\01\技术\笔记\md文档\Web.assets\wps252C.tmp.jpg) 

定时跳转

![img](D:\01\技术\笔记\md文档\Web.assets\wps252D.tmp.jpg) 

 

history

![img](D:\01\技术\笔记\md文档\Web.assets\wps252E.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps252F.tmp.jpg) 

 

 

 

 

 

 

 

 

***\*ES6\****

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2530.tmp.jpg) 

 

Js实际上是ECMAScript的实现和扩展

ECMAScript是一个标准化语法规范

[ES6 入门教程 - ECMAScript 6入门](https://es6.ruanyifeng.com/)

 

***\*let关键字\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps2531.tmp.jpg) 

 

2. var定义变量在代码块，作用域不受局限（函数受局限），let定义变量在代码块，作用域受局限

 

***\*const关键字\****

就像java中的final

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2532.tmp.jpg) 

禁止数组引用的更改但不禁止数组元素的更改

对象也是同理

 

 

***\*允许构造函数方式创建对象\****

![img](D:\01\技术\笔记\md文档\Web.assets\wps2533.tmp.jpg) 

 

 

***\*原型对象\****

每个对象都有1个原型对象，可使用原型对象的所有属性方法

和父类对象概念不一样的

![img](D:\01\技术\笔记\md文档\Web.assets\wps2534.tmp.jpg) 

随意指定1个对象，等于获得所有对象属性方法

 

***\*原型继承、继承链\****

可以指定对象，绑定，原型继承

![img](D:\01\技术\笔记\md文档\Web.assets\wps2535.tmp.jpg) 

 

A原型继承B，B原型继承C，A间接原型继承C，3者间继承关系呈链条

继承链 就是 多层原型继承

object是继承点顶层

 

 

 

 

至此，JavaScript暂告一段落

 

 

 

 

 

 

 

 

# json

 

 

JSON 是一种轻量级的数据交换格式

JavaScript Object Notation (JavaScript 对象表示法)，和JavaScript 的 对象字面量 表示法 一样

因为Js但独立于 JavaScript，可以在多种编程语言中使用。

JSON 比 XML 更小、更快，更易解析。

JSON 易于人阅读和编写。

JSON 数据可使用 AJAX 进行传输

 

 

主要由对象（用花括号{}表示）和数组（用方括号[]表示）组成。

例如

 

{"name": "John", "age": 30, "city": "New York"}，其中name、age和city是对象的属性，对应的"John"、30和"New York"是属性值。

数组可以包含多个值，如["apple", "banana", "cherry"]

↓涉及JSON语法规则，下面会说

 

 

***\*JSON - 转换为 JavaScript 对象\****

由于JSON 文本格式在语法上与创建 JavaScript 对象的代码相同。它转js对象无需解析器

JavaScript 程序能够使用内建的 eval() 函数，用 JSON 数据来生成原生的 JavaScript 对象。

eval() 将字符串作为 JavaScript 代码进行解析和执行

 

 

 eval() 函数可编译并执行***\*任何\**** JavaScript 代码。有潜在的安全问题。

当eval()函数用于处理用户输入（例如从 URL 参数、表单数据或其他外部来源获取的内容）时，如果没有对输入进行充分的验证和过滤，就存在注入JS代码的可能。

使用 JSON 解析器将 JSON 转换为 JavaScript 对象是更安全的做法。JSON 解析器只能识别 JSON 文本，而不会编译脚本。

 

基本上浏览器都内置json解析器

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2536.tmp.jpg) 

 

花括号 {} 保存的对象是一个 无序 的 键值对 集合。

中括号 [] 保存的是 值 的有序集合。

值 是 字符串（string）、数值(number)、布尔值、 null、对象（object）、数组（array）、JavaScript 的表达式（包括函数，日期，及 undefined），它们是可以嵌套的。

[]可以出现也可以不出现

 

它们依照规则组合，有丰富的数据表现形式

 

 

 

 

***\*JSON\****  ***\*vs\**** ***\*XML\****

 

JSON 和 XML 都用于接收 web 服务端的数据

JSON 和 XML写法不同

![img](D:\01\技术\笔记\md文档\Web.assets\wps2537.tmp.jpg) 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2538.tmp.jpg) 

 

 

可以通过数组或键的方式访问JSON数据

 

可循环访问json

 

var myObj = { "name":"runoob", "alexa":10000, "site":null }; 

for (x in myObj) { 

document.getElementById("demo").innerHTML += myObj[x] + "<br>"; 

或

document.getElementById("demo").innerHTML += x + "<br>";

}

 

不能使用 myObj.x		因为myObj里没有x这个东西

document.getElementById("demo").innerHTML += myObj[x] + "<br>";

 

 

 

 delete 关键字来删除 JSON 里的元素

delete 运算符将该值置为 undefined，但仍会保留空间，即将其变为稀疏数组（《JS权威指南》7.5节）。

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2539.tmp.jpg) 

就是把json对象变成字符串，当串儿使

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps253A.tmp.jpg) 

 

 

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps253B.tmp.jpg) 

访问服务器，服务器一般传回来字符串，可以用该语法把传回的字符串转为js对象，或用函数转为特定对象

 

使用该语法必须保证解析对象为标准的 JSON 格式，否则会解析出错。

网上有很多解析工具

 

 

实例

![img](D:\01\技术\笔记\md文档\Web.assets\wps253C.tmp.jpg) 

 

AJAX解析JSON

![img](D:\01\技术\笔记\md文档\Web.assets\wps254D.tmp.jpg) 

 

 

JSON 不能直接存储 Date 对象。

需要将其转换为字符串之后再转为 Date 对象

 

两种方式

![img](D:\01\技术\笔记\md文档\Web.assets\wps254E.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps254F.tmp.jpg) 

 

 

函数也是

![img](D:\01\技术\笔记\md文档\Web.assets\wps2550.tmp.jpg) 

 

主流浏览器都支持 JSON.parse() 函数：

旧版浏览器可以使用第三方库来支持：https://github.com/douglascrockford/JSON-js

 

 

 

eval的一些其它用法

![img](D:\01\技术\笔记\md文档\Web.assets\wps2551.tmp.jpg) 

 

 

json字符串要做对象化处理，同时被eval处理时注意加上‘（’		‘）’

因为json以{}表达开始结束，eval认为它是代码块

所以要转为表达式，碰巧了，语法格式问题。

![img](D:\01\技术\笔记\md文档\Web.assets\wps2552.tmp.jpg) 

 

 

 

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2553.tmp.jpg) 

 

 

 

***\*JSON.stringify()\****

 

可以使用 JSON.stringify() 方法将 JavaScript 对象转换为字符串。

 

语法:

JSON.stringify(value, replacer, space)

 

value：必需参数，要转换为 JSON 字符串的 JavaScript 对象或值。可以是对象、数组、数字、字符串、布尔值或null

 

replacer：可选参数，是一个函数或一个数组。用于对转换后结果（字符串） 进行特定 筛选或转换，不使用就写null或空着 ？？？。

replacer是函数时，该函数会对对象的每个属性（包括嵌套对象的属性）进行处理。

函数接收两个参数，第一个是属性名（如果是数组元素，则为索引），第二个是 属性值。函数应该返回处理后的属性值，如果返回 undefined，则排除函数处理的成员。根对象的键是一个空字符串："" 。

例如：

 

let person = { name: "Alice", age: 25, city: "New York" };

let jsonStr = JSON.stringify(person, (key, value) => {

  if (key === "age") {

​    return value + 1; // 将年龄加1后转换

  }

return value;});

console.log(jsonStr); // 输出: {"name":"Alice","age":26,"city":"New York"}

 

replacer是数组时，只有数组中包含的属性名对应的属性会被包含在转换后的 JSON 字符串中。

 

例如：

 

let student = { name: "Bob", age: 20, grade: "A" };

let jsonStr = JSON.stringify(student, ["name", "grade"]);

console.log(jsonStr); // 输出: {"name":"Bob","grade":"A"}

 

 

 

space：可选参数，文本添加缩进、空格和换行符，如果是一个数字，则返回值文本在 每个级别 缩进指定数目的空格，如果 space 大于 10，则文本缩进 10 个空格。space 也可以使用非数字，如：\t。

 

例如：

let data = { a: 1, b: { c: 2 } };

let jsonStr = JSON.stringify(data, null, 2);

console.log(jsonStr);

/*

输出: 

{

 "a": 1,

 "b": {

  "c": 2

 }

}

*/

 

 

***\*stringify\*******\*对象和数组转换\****

var obj = { "name":"runoob", "alexa":10000, "site":"www.runoob.com"};

var myJSON = JSON.stringify(obj);

var arr = [ "Google", "Runoob", "Taobao", "Facebook" ];

var myJSON = JSON.stringify(arr);

 

 

Js中存在Date概念，但JSON不能存储 Date 对象，所以要转为字符串

JSON.stringify() 会将所有Date对象 转换为字符串

var obj = { "name":"Runoob", "initDate":new Date(), "site":"www.runoob.com"};

var myJSON = JSON.stringify(obj);

 

JSON 不允许包含函数，JSON.stringify() 会删除 JavaScript 对象的函数，包括 key 和 value。

var obj = { "name":"Runoob", "alexa":function () {return 10000;}, "site":"www.runoob.com"};

var myJSON = JSON.stringify(obj);

![img](D:\01\技术\笔记\md文档\Web.assets\wps2554.tmp.jpg) 

所以在执行 JSON.stringify() 前 将函数转换为字符串 ：

var obj = { "name":"Runoob", "alexa":function () {return 10000;}, "site":"www.runoob.com"};

obj.alexa = obj.alexa.toString();

var myJSON = JSON.stringify(obj);

 

 

***\*数据类型转换细节\****

对象转换：当转换对象时，对象的所有可枚举属性（通过for...in循环可访问的属性）会被转换。

非枚举属性（如通过Object.defineProperty()定义的不可枚举属性）默认不会被转换，除非在replacer函数中专门处理这些属性。

例如：

 

let nonEnumerableObj = {};

Object.defineProperty(nonEnumerableObj, "secret", {

  value: "This is a secret",

enumerable: false});

console.log(JSON.stringify(nonEnumerableObj)); // 输出: {}

 

特殊数据类型转换：

undefined、任意函数和Symbol值在默认情况下会被忽略。例如：

 

let complexObj = { a: 1, b: undefined, c: function() {}, d: Symbol("test") };

console.log(JSON.stringify(complexObj)); // 输出: {"a":1}

 

NaN和Infinity会被转换为null。例如：

 

let numObj = { a: NaN, b: Infinity };console.log(JSON.stringify(numObj)); // 输出: {"a":null,"b":null}

 

日期对象（Date）会被转换为 ISO 格式的日期字符串。例如：

 

let date = new Date();console.log(JSON.stringify(date)); // 输出: "2024-11-07T00:00:00.000Z"（具体日期时间根据当前时间而定）

 

应用场景举例

网络数据传输：在 Web 开发中，通过fetch或XMLHttpRequest发送数据到服务器时，需要将 JavaScript 对象转换为服务器能够理解的格式。例如：

 

let userData = { username: "user1", password: "pass1" };fetch('https://example.com/api/login', {

  method: 'POST',

  headers: {

​    'Content - Type': 'application/json'

  },

  body: JSON.stringify(userData)});

 

本地存储数据保存：将数据保存到浏览器的本地存储中，以便在下次访问页面时使用。例如：

let shoppingCart = [

  { product: "Apple", price: 1.0 },

{ product: "Banana", price: 0.5 }

];

localStorage.setItem('cart', JSON.stringify(shoppingCart));

 

 

***\*JSONP\****	***\*(JSON with Padding)\**** 

因为***\*同源策略\****的原因，json需要该技术
同源策略（Same - Origin Policy）是浏览器的一个安全机制，用于限制文档或脚本与不同源的资源进行交互。

简单来说，它规定了网页脚本只能访问与它同源的资源，这里的 “源” 包括协议（如 http、https）、域名（如[example.com](https://example.com/)）和端口（如 80、443）。只有当这三个部分完全相同的时候，才被认为是同源。

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2555.tmp.jpg) 

JsonNP让 json脚本满足了同源策略，可以跨域读取数据

***\*如何使用JSONP进行跨域数据获取？\****

***\*客户端实现步骤\****

***\*步骤一：定义回调函数\****

 

回调函数是用于接收从跨域服务器返回的数据的函数。这个函数的参数通常就是服务器返回的 JSON 数据。例如，你想要获取用户信息，定义的回调函数可以如下：

function userInfoCallback(data) {

  console.log("用户姓名：", data.name);

  console.log("用户年龄：", data.age);
}

**·** ***\*步骤二：创建并插入\*******\*<script>\*******\*标签\****

通过动态创建<script>标签来发起跨域请求。

将<script>标签的src属性设置为跨域服务器提供 JSONP 服务的 URL，并在 URL 中添加一个参数，用于指定之前定义的回调函数名称。

例如，如果跨域服务器提供 JSONP 服务的 URL 是https://example.com/api/jsonp，则代码如下：

var script = document.createElement('script');// 假设服务器期望接收的回调函数参数名为callback
script.src = 'https://example.com/api/jsonp?callback=userInfoCallback';document.head.appendChild(script);

 

***\*步骤三：清理<script>标签（可选）\****

为了避免重复请求或者内存泄漏等问题，在数据获取完成后，可以将插入的<script>标签从文档中移除。

这可以在回调函数内部实现，例如：

function userInfoCallback(data) {

  console.log("用户姓名：", data.name);

  console.log("用户年龄：", data.age);

  // 获取刚刚插入的script标签

  var script = document.getElementsByTagName('script')[document.getElementsByTagName('script').length - 1];

  // 从文档头部移除script标签

document.head.removeChild(script);

}

 

 

服务器端实现步骤（以 Node.js 为例）

 

步骤一：解析请求参数

当服务器接收到客户端的请求时，需要从请求中获取回调函数的名称。在 Node.js 中，如果使用 Express 框架，可以这样做：

 

收起

 

javascript

复制

const express = require('express');const app = express();

 

app.get('/api/jsonp', (req, res) => {

  // 获取回调函数名称

  const callback = req.query.callback;

  // 假设要返回的数据

  const data = {

​    name: "John",

​    age: 30

  };

  // 将数据包装在回调函数中

  const jsonpData = callback + "(" + JSON.stringify(data) + ")";

  res.send(jsonpData);});

 

app.listen(3000, () => {

  console.log("服务器在3000端口运行");});

 

步骤二：返回包装后的 JSON 数据

服务器获取回调函数名称后，将真正要发送的 JSON 数据包装在回调函数调用的形式中，然后将这个包装后的内容返回给客户端。例如，在上面的代码中，jsonpData就是包装后的内容，通过res.send(jsonpData)发送给客户端。

 

需要注意的是，JSONP 只能用于 GET 请求，因为它是基于<script>标签的加载机制。并且，由于 JSONP 依赖于执行服务器返回的 JavaScript 代码，所以存在一定的安全风险，如可能会遭受跨站脚本攻击（XSS），在使用时要确保服务器来源可靠并且数据经过适当验证。

 

JSON的Key必须包裹在一个双引号中，在实践中，编写 JSON 的时候，忘了给 Key 值加双引号或者是把双引号写成单引号是常见错误。

JSON的值只能是以下几种数据格式，其他任何格式都会触发报错，例如 JavaScript 中的 undefined。

数字，包含浮点数和整数

字符串，需要包裹在双引号中

Bool值，true 或者 false

数组，需要包裹在方括号中 []

对象，需要包裹在大括号中 {}

Null

还需要注意的是 JSON 文件中无法使用注释，试图添加注释将会引发报错。

 

 

 

# VUE

 

渐进式前端框架

渐进式就是想用就用，不想用就不用，不着急，慢慢了解，循序渐进

底层是Js

 

***\*2个核心功能\****

声明式渲染：基于html标准语法扩展，通过简单描述可以实现html和js状态间关系

响应式：在js变化时相应更新DOM

 

 

 

 

***\*大杂烩\****

 

 



服务端和客户端使用json传递数据，双方都是传递的字符串吗？

客户端发送数据到服务端

在客户端向服务端传递数据时，通常会将 JavaScript 对象转换为 JSON 字符串后发送。这是因为 HTTP 协议主要是基于文本传输的，而 JSON 格式作为一种轻量级的文本数据格式，非常适合在网络中传输数据。

例如，在 JavaScript 中使用fetch API 发送数据：

 

收起

 

javascript

复制

let userData = {

  name: "John",

  age: 30};fetch('https://example.com/api/user', {

  method: 'POST',

  headers: {

​    'Content - Type': 'application/json'

  },

  body: JSON.stringify(userData)});

 

这里将userData对象转换为 JSON 字符串后，放在fetch请求的body部分发送给服务端。服务端接收到的是一个 JSON 字符串，需要在服务端进行解析。

 

服务端发送数据到客户端

服务端在向客户端发送数据时，也会将数据转换为 JSON 字符串。例如，在一个 Node.js 的 Express 应用中：

 

收起

 

javascript

复制

const express = require('express');const app = express();const port = 3000;

 

app.get('/api/user', (req, res) => {

  let userData = {

​    name: "Alice",

​    age: 25

  };

  res.json(userData);});

 

app.listen(port, () => {

  console.log(`服务器在${port}端口运行`);});

 

在这个例子中，res.json(userData)会自动将userData对象转换为 JSON 字符串，并设置正确的Content - Type响应头（application/json）发送给客户端。客户端接收到这个 JSON 字符串后，可以使用JSON.parse方法将其转换为 JavaScript 对象进行处理。

 

特殊情况说明

虽然 JSON 字符串是最常见的传输方式，但在某些情况下，也可能不直接传输 JSON 字符串。例如：

客户端直接发送文本数据：如果客户端只是简单地发送一个文本信息，如用户在表单中输入的一个评论内容，那么可以直接将这个文本发送给服务端，而不需要将其包装成 JSON 对象再转换为字符串。但如果要同时发送多个相关的数据（如用户 ID、评论内容、评论时间等），使用 JSON 格式会更加方便和结构化。

服务端返回非 JSON 数据格式：服务端有时候可能会返回其他格式的数据，如纯文本、HTML 片段、XML 等。这取决于具体的应用场景。例如，服务端返回一个 HTML 页面给客户端浏览器进行渲染，或者返回一个 XML 格式的配置文件给客户端进行解析。不过，在现代 Web 开发中，尤其是涉及到前后端分离的架构和 API 接口通信时，JSON 是非常主流的数据传输格式。

 

 

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2565.tmp.jpg) 

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2566.tmp.jpg) 

 

 

 

 

浏览器按照编写顺序依次执行每条语句。

 

js区分大小写

 

JavaScript 使用 Unicode 字符集。

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2567.tmp.jpg) 

 

 

 

 

 

 

 

# JavaWeb

 

BS和CS

![img](D:\01\技术\笔记\md文档\Web.assets\wps2568.tmp.jpg) 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2569.tmp.jpg) 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps256A.tmp.jpg) 

 

 

 

 

BS通信原理

输入网址，转为ip，通过唯一ip的唯一端口，确定资源所在位置

![img](D:\01\技术\笔记\md文档\Web.assets\wps256B.tmp.jpg) 

 

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps256C.tmp.jpg) 

 

 

Tomcat

![img](D:\01\技术\笔记\md文档\Web.assets\wps256D.tmp.jpg) 

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps257E.tmp.jpg) 

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps257F.tmp.jpg) 

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2580.tmp.jpg) 

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2581.tmp.jpg) 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2582.tmp.jpg) 

win系统的cmd是gbk

 

 

 

BS结构系统角色和协议

举例

![img](D:\01\技术\笔记\md文档\Web.assets\wps2583.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2584.tmp.jpg) 

 

 

## Servlet	服务程序



Servlet是接口，也是规范

 

遵循Servlet规范 实现服务器和Webapp通信的话，web程序员要做两件事，实现Servlet接口、将实现类（每个请求的资源路径对应的类）配置到配置文件（指定请求路径和类名的关系）

Servlet也实现了Web服务器和WebApp解耦合

  

![img](D:\01\技术\笔记\md文档\Web.assets\wps2585.tmp.jpg) 

JavaEE9开始，Servlet从javax转移至jakarta

![img](D:\01\技术\笔记\md文档\Web.assets\wps2586.tmp.jpg) 

不过官方提供了迁移工具

 

 

 

 

### 开发1个Servlet规范的webApp

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps2587.tmp.jpg) 

然后创建如下：

![img](D:\01\技术\笔记\md文档\Web.assets\wps2588.tmp.jpg) 

classer存的类

lib存的依赖包

web.xml的内容：

![img](D:\01\技术\笔记\md文档\Web.assets\wps2589.tmp.jpg) 

描述信息和映射信息中servlet-name需一致

 

 

 

web.xml里是class和路径名的映射，classes里是类，bin是类依赖的包

 

 

 

 

 ![img](D:\01\技术\笔记\md文档\Web.assets\wps259A.tmp.jpg)

Tomcat便根据![img](D:\01\技术\笔记\md文档\Web.assets\wps259B.tmp.jpg)路径找到类然后找到对应方法

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps259C.tmp.jpg) 

 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps259D.tmp.jpg) 

![img](D:\01\技术\笔记\md文档\Web.assets\wps259E.tmp.jpg) 

 

 

### 	服务器向浏览器返回内容，可以指定普通文本或html代码

![img](D:\01\技术\笔记\md文档\Web.assets\wps259F.tmp.jpg) 

 

 

 使用超链接访问Tomcat上应用

 

每次都要手动输入麻烦，写好超链接直接点就行，这个html文件不能在WEB_INF里

 

 

 

 

### 	Servlet的方法

![img](D:\01\技术\笔记\md文档\Web.assets\wps25A0.tmp.jpg) 

 

 

### Servlet对象生命周期

 

Servlet对象生命周期由Web容器管理，Web容器会把它们放在1个HashMap容器里，不在HaspMap里的Servlet对象不受管理，自己new的Servlet对象不在HaspMap里

 

 

默认情况下 ，Web服务器 启动时Servlet对象不会实例化，而是将	路径与类名	放入HashMap

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps25A1.tmp.jpg) 

加上这么一句，就会服务器启动时实例化，数字越小优先级越高

 

 

 

假设有个Servlet对象AServlet，用户第一次发送请求，init和service方法均调用，之后重新请求，只调用service。说明Servlet对象是单例模式，但因为Servlet对象符合单例模式，Servlet类不是单例模式，且构造方法不是私有的，所以是假单例

 

关闭服务器前，Web服务器调用destory方法销毁Servlet对象

 

 

Servlet构造方法、init方法、destory只执行1次，service方法=请求数

 

 

对于构造方法，

![img](D:\01\技术\笔记\md文档\Web.assets\wps25A2.tmp.jpg) 

 

init更好的替代了构造方法

 

 



 

### GenericServlet

 每个类实现Servlet接口，需要实现Servlet中所有方法，即使这些方法会有用不到的（Servlet常用方法只有service()）

为此通过**适配器模式**优化Servlet方法

![img](D:\01\技术\笔记\md文档\Web.assets\wps25A3.tmp.jpg) 

 

![img](D:\01\技术\笔记\md文档\Web.assets\wps25A4.tmp.jpg) 

GenericServlet实现所有Servlet方法，之后继承它即可



![img](D:\01\技术\笔记\md文档\Web.assets\wps25A5.tmp.jpg) 

执行父类init方法

初始化Servlet对象

因为init方法需要ServletConfig对象，所以先创建ServletConfig对象，再调用init方法

 

 

```java
 //GenericServlet 代码

import javax.servlet.Servlet;

import javax.servlet.ServletConfig;

import javax.servlet.ServletException;

import javax.servlet.ServletRequest;

import javax.servlet.ServletResponse;

import java.io.IOException;

 

// 实现了 Servlet 和 ServletConfig 接口
public abstract class GenericServlet implements Servlet, ServletConfig {

  private transient ServletConfig config;

  // 实现 Servlet 接口的 init 方法

  @Override

  public void init(ServletConfig config) throws ServletException {

	this.config = config;

    this.init();
      //为了防止子类重写导致父类私有属性config为null

  }
  // 一个默认的无参 init 方法，子类可重写进行自定义初始化

  public void init() throws ServletException {

​    // 空实现，子类可根据需要重写

  }

 

  // 实现 Servlet 接口的 getServletConfig 方法

  @Override

  public ServletConfig getServletConfig() {

​    return config;

  }

 

  // 实现 Servlet 接口的 service 方法，这是抽象方法，子类必须实现
  // 只有service是抽象方法，因为多态需求

  @Override

  public abstract void service(ServletRequest req, ServletResponse res)

​      throws ServletException, IOException;

 

  // 实现 Servlet 接口的 getServletInfo 方法

  @Override

  public String getServletInfo() {

​    return "";

  }

 

  // 实现 Servlet 接口的 destroy 方法

  @Override

  public void destroy() {

​    // 空实现，子类可根据需要重写进行资源释放等操作

  }

 

  // 实现 ServletConfig 接口的 getServletName 方法

  @Override

  public String getServletName() {

​    return config.getServletName();

  }

 

  // 实现 ServletConfig 接口的 getServletContext 方法

  @Override

  public javax.servlet.ServletContext getServletContext() {

​    return config.getServletContext();

  }

 

  // 实现 ServletConfig 接口的 getInitParameter 方法

  @Override

  public String getInitParameter(String name) {

​    return config.getInitParameter(name);

  }

 

  // 实现 ServletConfig 接口的 getInitParameterNames 方法

  @Override

  public java.util.Enumeration<String> getInitParameterNames() {

​    return config.getInitParameterNames();

  }}
```

 

如果子类重写init方法，会导致GenericServlet （父类）config不能被正确赋值

为了避免这种情况

#### 情况一：子类没有重写 `init(ServletConfig config)` 方法

当子类没有重写 `init(ServletConfig config)` 方法时，Servlet 容器调用该方法时会执行 `GenericServlet` 中的 `init(ServletConfig config)` 方法。然后在这个方法内部会调用 `this.init()`，这里又分两种情况：

- **子类没有重写 `init()` 方法**：此时会执行父类 `GenericServlet` 中 `init()` 方法的空实现。
- **子类重写了 `init()` 方法**：那么会执行子类重写后的 `init()` 方法逻辑，例如：



```java
import javax.servlet.GenericServlet;
import javax.servlet.ServletConfig;
import javax.servlet.ServletException;

public class MyServlet extends GenericServlet {
    @Override
    public void init() throws ServletException {
        System.out.println("MyServlet 自定义初始化逻辑");
    }
}
```

当 Servlet 容器创建 `MyServlet` 实例并调用 `init(ServletConfig config)` 方法时，最终会执行子类重写的 `init()` 方法，输出 “MyServlet 自定义初始化逻辑”。

#### 情况二：子类重写了 `init(ServletConfig config)` 方法

- **正确重写（调用父类方法）**：

```java
import javax.servlet.GenericServlet;
import javax.servlet.ServletConfig;
import javax.servlet.ServletException;

public class MyServlet extends GenericServlet {
    @Override
    public void init(ServletConfig config) throws ServletException {
        super.init(config); // 调用父类的 init(ServletConfig config) 方法
        System.out.println("MyServlet 额外的初始化逻辑");
    }

    @Override
    public void init() throws ServletException {
        System.out.println("MyServlet 自定义的无参 init 逻辑");
    }
}
```

当 Servlet 容器调用 `MyServlet` 的 `init(ServletConfig config)` 方法时，由于在子类重写方法中调用了 `super.init(config)`，会先执行父类的 `init(ServletConfig config)` 方法，该方法内部会调用 `this.init()`，此时刻后 `this` 代表当前子类对象，所以会执行子类重写后的 `init()` 方法，输出 “MyServlet 自定义的无参 init 逻辑”，然后再执行子类 `init(ServletConfig config)` 方法中剩余的逻辑，输出 “MyServlet 额外的初始化逻辑”。

- **错误重写（未调用父类方法）**：



```java
import javax.servlet.GenericServlet;
import javax.servlet.ServletConfig;
import javax.servlet.ServletException;

public class MyServlet extends GenericServlet {
    @Override
    public void init(ServletConfig config) throws ServletException {
        // 没有调用 super.init(config)
        System.out.println("MyServlet 错误的初始化逻辑");
    }

    @Override
    public void init() throws ServletException {
        System.out.println("MyServlet 自定义的无参 init 逻辑");
    }
}
```

这种情况下，父类 `init(ServletConfig config)` 方法不会被执行，也就不会调用子类重写的 `init()` 方法，只会执行子类重写的 `init(ServletConfig config)` 方法中的逻辑，输出 “MyServlet 错误的初始化逻辑” ，而且父类的 `config` 成员变量也不会被正确赋值。

综上所述，子类重写 `init(ServletConfig config)` 方法时并不一定会执行父类的 `init()` 方法，具体执行哪个 `init()` 方法取决于子类是否重写了 `init()` 方法以及在重写 `init(ServletConfig config)` 方法时是否调用了父类的该方法。





上面算是对init()方法的详解，接下来是其他方法



#### ServletConfig

![image-20250125155620432](D:\01\技术\笔记\md文档\Web.assets\image-20250125155620432.png)

![image-20250125160013133](D:\01\技术\笔记\md文档\Web.assets\image-20250125160013133.png)



ServletConfig方法

![image-20250125173637294](D:\01\技术\笔记\md文档\Web.assets\image-20250125173637294.png)

 可以初始化Servlet信息

```xml
<init-param>

​	<param-name></param-name>

​	<param-value></param-value>

</init-param> 
```

![image-20250125160454250](D:\01\技术\笔记\md文档\Web.assets\image-20250125160454250.png)

 ![image-20250126100300879](D:\01\技术\笔记\md文档\Web.assets\image-20250126100300879.png)









#### ServeltContext



通过ServletConfig获取ServletContext

同一Webapp的所有Servlet对象获取的ServletContext一样

ServletContext对应web.xml文件

![image-20250125205401268](D:\01\技术\笔记\md文档\Web.assets\image-20250125205401268.png)

 

![image-20250126112015589](D:\01\技术\笔记\md文档\Web.assets\image-20250126112015589.png) 



**`context - param`**：适合配置整个应用共享的参数，比如全局的缓存策略配置、公共文件的存储路径等，这些参数不依赖于具体的 Servlet，是整个应用都可能用到的。

**`init - param`**：适用于为特定 Servlet 提供个性化的配置信息，如某个 Servlet 连接特定数据库的用户名、密码等，不同的 Servlet 可以有各自独立的初始化参数。



![image-20250126112331021](D:\01\技术\笔记\md文档\Web.assets\image-20250126112331021.png)

 

```java
 public class SServletContext extends GenericServlet{

    @Override
    public void service(ServletRequest request, ServletResponse response) throws ServletException, IOException {

        response.setContentType("text/html");
        PrintWriter out = response.getWriter();

        ServletContext application = this.getServletConfig().getServletContext();
        out.print(application);

        Enumeration<String> en = application.getInitParameterNames();
        while(en.hasMoreElements()){
            String key = en.nextElement();
            String value = application.getInitParameter(key);
            out.print(key + "=" + value);
            
        }
    }
```

 

```java
//获取上下文的根
String contextPath = application.getContextPath();
out.println(contextPath + "<br>");
```





```java
//获取文件绝对路径
String realPath = config.getRealPath("index.html");
String realPath = config.getRealPath("/index.html");
/代表根路径，加不加都可以，反正默认是从根路径开始找
```

 





 ![image-20250126113429019](D:\01\技术\笔记\md文档\Web.assets\image-20250126113429019.png)

 如果使用的是原始开发工具，log会被记录在Tomcat里的logs里

 ![image-20250126114123902](D:\01\技术\笔记\md文档\Web.assets\image-20250126114123902.png)

 ![image-20250126114326810](D:\01\技术\笔记\md文档\Web.assets\image-20250126114326810.png)

 

 

```java

        response.setContentType("text/html");
        PrintWriter out = response.getWriter();

        ServletContext application = this.getServletConfig().getServletContext();

        User user = new User("zhangsan", "asdasd");
        application.setAttribute("userOne",user);
        Object obj = application.getAttribute("userOne");
        out.print(obj + "<br>");

```

 

  

 ![image-20250126130329365](D:\01\技术\笔记\md文档\Web.assets\image-20250126130329365.png)

 



### HttpServlet

 B/S架构基于HTTP协议，Servlet专门提供了一个HTTPSerlvet协议，继承它，而不继承GenericServlet



目前为止接触的缓存机制

堆内存

![image-20250126132215327](D:\01\技术\笔记\md文档\Web.assets\image-20250126132215327.png)

![image-20250126132241937](D:\01\技术\笔记\md文档\Web.assets\image-20250126132241937.png)



在学习HttpServlet相关内容前，先补充HTTP协议相关内容

#### Http协议

W3C制定的超文本传输协议



 查看协议内容

F12->network

![image-20250127132049668](D:\01\技术\笔记\md文档\Web.assets\image-20250127132049668.png)





HTTP请求协议

​	**B->S**

​		请求行

​		请求头

​		空白行

​		请求体

​		//  HTTP请求协议具体报文

![image-20250127132704839](D:\01\技术\笔记\md文档\Web.assets\image-20250127132704839.png)

![image-20250127132800825](D:\01\技术\笔记\md文档\Web.assets\image-20250127132800825.png)





![image-20250127133023456](D:\01\技术\笔记\md文档\Web.assets\image-20250127133023456.png)

![image-20250127133112372](D:\01\技术\笔记\md文档\Web.assets\image-20250127133112372.png)

![image-20250127133117475](D:\01\技术\笔记\md文档\Web.assets\image-20250127133117475.png)









​	**S->B**

​		状态行

​		响应头

​		空白行

​		响应体

​		// HTTP响应协议具体报文

![image-20250127132255297](D:\01\技术\笔记\md文档\Web.assets\image-20250127132255297.png)

![image-20250127132434685](D:\01\技术\笔记\md文档\Web.assets\image-20250127132434685.png)



![image-20250127132522299](D:\01\技术\笔记\md文档\Web.assets\image-20250127132522299.png)

 

 

 怎么向服务器发送GET或POST请求？

 2021年1月27日

到目前为止，只有1种情况发送POST请求：使用form表单，且form标签中method属性值为：method=“post”

其他像是在浏览器地址栏输入URL，敲回车等一律属于get请求  

![image-20250127134706297](D:\01\技术\笔记\md文档\Web.assets\image-20250127134706297.png)

 get绝对安全，因为是从服务器获取数据

post向服务器发送数据，存在风险

get支持缓存，post不支持（就是第1次加载页面慢，但以后就快了）

![image-20250127135120535](D:\01\技术\笔记\md文档\Web.assets\image-20250127135120535.png)

  



简单了解设计模式

![image-20250127135722609](D:\01\技术\笔记\md文档\Web.assets\image-20250127135722609.png)

- 模板方法设计模式

    ![image-20250127141136242](D:\01\技术\笔记\md文档\Web.assets\image-20250127141136242.png)

![image-20250127141027388](D:\01\技术\笔记\md文档\Web.assets\image-20250127141027388.png)





#### HttpServlet源码分析

它专门为http协议准备的，比GenericServlet更适合Http协议下开发

在jakarta.servlet.http.HttpServlet包下



如果重写srevice方法，就不能使用父类service方法，进而就不能有405等报错提示

![image-20250127154014440](D:\01\技术\笔记\md文档\Web.assets\image-20250127154014440.png)

错误提示的存在是有意义的



设置欢迎界面

创建1个html页面

web.xml中添加

![image-20250128094154101](D:\01\技术\笔记\md文档\Web.assets\image-20250128094154101.png)

看到路径不需以/开头

![image-20250128102933309](D:\01\技术\笔记\md文档\Web.assets\image-20250128102933309.png)

![image-20250128103006303](D:\01\技术\笔记\md文档\Web.assets\image-20250128103006303.png)

​	

也可以把Servlet配置成欢迎界面



WEB-INF目录

- 该目录下的资源受到保护，不可在浏览器通过直接路径访问



#### HttpServlt接口详解

![image-20250128113850367](D:\01\技术\笔记\md文档\Web.assets\image-20250128113850367.png)



![image-20250128190902684](D:\01\技术\笔记\md文档\Web.assets\image-20250128190902684.png)



#### 请求域对象

request对象 又称为 请求域 对象

- **应用域**对象

    - ServletContext（Servlet上下文对象）

        - 上文提及的每个webapp对应1个的操作共享、很少操作、数据量少的对象，提供操作数据的方法

            

实际上向应用域中绑定数据，就相当于数据放到缓存中，减少IO操作，提高性能，是提高系统性能的重要缓存技术

缓存技术常见的有  线程池、数据库连接池、线程池 



请求区域对象比应用域对象范围、声明周期小很多

请求域只在1次请求内有效



请求域和应用域都有操作 数据共享域 方法，方法也大致相同

![image-20250129164555587](D:\01\技术\笔记\md文档\Web.assets\image-20250129164555587.png)





​	请求转发

假设AB两个继承HttpServlet，A绑定数据域，B从域中请求数据

绑定和请求操作分在2次请求中完成

B无法请求到，因为是2次不同请求（别忘了请求域的生命周期）

如果想实现，可以使用**请求转发**

其实就是为了避免请求挂掉，一个请求中调用另一个请求



别忘了，自己new的能实现，但new的对象不受Tomcat管理



实现请求转发可以用**转发器**

使用**request.getRequestDispatcher（"path"）**方法得到转发器（Dispatcher）

request（请求）去得到转发器



本质都是new对象，但Tomcat根据路径去映射类，和自己new的不一样

![image-20250129170428103](D:\01\技术\笔记\md文档\Web.assets\image-20250129170428103.png)



接着，使用转发器的**forward（request， response）**方法

```java
request.getRequestDispatcher("\b").forward(request, response);
```

request, response这2个参数是A的，都传给B对象，B使用doGet()接收

​	同一request对象代表同一请求

  

这样就实现了Servlet间（不只1对1）传递资源（只要在Tomcat中合法）。相较ServletContext更省资源

注意：转发路径不加项目名，以“/”开头 



#### 易混淆方法比较+常用方法

```java
String username = request.getParameter("username");
//获取用户在浏览器提交的数据（来自浏览器）

//一定先执行过request.setAttribute("name", new Object());
//attribute	属性
Object obj = request.getAttribute("name");
//获取请求域当中绑定的数据
```



```java
//得到客户端地址	remote 远程
String remoteAddr = http_servlet_request.getRemoteAddr();

//设置请求体字符集
//get请求在请求行提交数据
//post请求在请求体提交数据
//显然，给post用的
//tomcat9以及之前，中文会乱码，10之后请求体字符集是utf-8，不用担心
request.setCharacterEncoding("utf-8");

```

![image-20250131194354108](D:\01\技术\笔记\md文档\Web.assets\image-20250131194354108.png)

```java
//接上文
//动态获取应用根路径
String str = request.getContextPath();

……
```









Servlet实现单表CRUD操作

```sql
drop table if exists depts;
create table depts{
	deptno int primary key,
	dename varchar(255),
	loc varchar(255)
};
insert into depts(deptno, dename, loc) values(10,"研发部","济南");
commit;
select * form depts;
```





web应用中有2种方式完成资源跳转

- 转发

    - ```java
        //获取请求转发器对象
        RequestDispatcher dispatcher = request.getRequestDispatcher("/dept/list");
        dispatcher.forward(request,response);
        ```

        

        转发是1次请求

        跳转动作完全在Web服务器内部完成

        

- 重定向

    - ```java
        //记得加项目名，因为重定向相当于浏览器发送请求，浏览器发送请求请求路径上需要加项目名
        response.sendRedirect("/oa/servlet10/b");
        
        //此路径发给浏览器，浏览器自发向服务器发送请求
        ```



​		重定向是2次请求

​		跳转动作由浏览器完成

转发和重定向的选择

- 如果AServlet中向request域绑定了数据，希望从BServlet中把request域中ASevlet数据取出来，用转发机制
    否则用重定向



转发有刷新问题，比如往数据库存了一条数据，存储成功后跳转刷新页面，如果反复刷新该页面，数据库也会重复存储数据。

```
这是因为转发本质上是一次请求，浏览器地址栏的 URL 不会改变。具体解释如下：

- **转发原理**：转发是在服务器内部完成的资源跳转，由`request`对象触发。当进行转发操作后，浏览器并不知道服务器内部的转发过程，它只认为是对当前请求的响应。所以当用户刷新页面时，浏览器会重新发送当前请求，由于之前的存储操作是在这个请求中完成的，因此会导致重复执行存储逻辑，造成数据库重复存储数据。


```



 

### Servlet中注解式开发

提高效率，便捷开发

#### 注解的形式

@注解名（属性名=属性值，属性名=属性值……） 















#### @WebServlet

```java
jakarta.servlet.annotation.weServlet

Servlet类上写@WebServlet
```

分担web.xml工作，xml负责经常修改的，@WebServlet负责很少修改的

例

![image-20250201132202159](D:\01\技术\笔记\md文档\Web.assets\image-20250201132202159.png)



当注解属性的值是个数组但只有1个元素，大括号可省略

![image-20250201133246687](D:\01\技术\笔记\md文档\Web.assets\image-20250201133246687.png)

 









通过注解获取对象

```java
if（welcomeServletClass.isAnnotationPresent(WebServlet.class)）{
    
    WebServlet webServletAnnotation = welcomeServletClass.getAnnotation(WebServlet.class);
    

}
```





注解解决了配置文件问题



还有问题，比如1个单表CRUD，就写了很多类，类太多了（因为1个请求对应1个Servlet类）



注解使用模板方法设计模式解决这个问题

​	模板方法设计模式上文提到过，模板类模板方法中定义核心算法骨架，具体实现步骤可以延伸到子类实现

可以改成：1个请求对应1个方法，1个业务对应1个Servlet类

```java
//模板类
@WevServlet({"/dept/list","/dept/save","/dept/modify","/dept/delete","/dept/detail","/dept/edit"})
	

	public class DeptServlet extends HttpServlet{
    //模板方法
    //重写service方法（没有重写doGet或doPost）
    @Override
    proteted void service(HttpServletRequest request, HttservletResponse response)
        throws ServletException, IOException {
    	
        String servletPath = request.getServletPath();
        if("/dept/list".equals(servletPath)){
            doList(request, response);
		}else if("/dept/save".equals(servletPath)){
            doSave();
		}else if("/dept/modify".equals(servletPath)){
            doModify();
		}
        
    }
        
}

//模板方法

```





纯粹Servlet开发Web应用的缺陷

​	到目前为止，前端代码都是在Servlet里写的，java本来就不是写前端的，前端在java里以字符串形式表示，容易出错，也不好维护





### JSP

JSP 即 Java Server Pages

JSP 页面由 HTML 代码和嵌入其中的 Java 代码所组成，能够将动态内容嵌入到静态的 HTML 页面中，使得网页可以根据不同的请求生成动态的响应结果。

**首次请求**：当客户端请求一个 JSP 页面时，服务器上的 JSP 引擎会将该 JSP 页面转译为一个 Java Servlet 类（.java 文件），这个过程包括解析 JSP 页面中的 HTML 标签、Java 代码等元素，并将其转换为 Servlet 类中的相应代码。接着，Servlet 类会被编译成字节码文件（.class 文件），然后由 Java 虚拟机加载并执行。

**后续请求**：如果后续再次请求该 JSP 页面，且 JSP 页面内容未发生变化，服务器会直接调用已编译好的 Servlet 类实例来处理请求，而无需再次进行转译和编译过程，提高了响应效率。





WEB-INF外创建1个index.jsp

访问它，底层执行index_jsp.class，所以它就是个Servlet类

![image-20250201145716044](D:\01\技术\笔记\md文档\Web.assets\image-20250201145716044.png)





















