# HTML

## 定义

HTML 是用来描述网页的一种"语言"

- HTML 指的是超文本标记语言 (**H**yper **T**ext **M**arkup **L**anguage)
- HTML 不是一种编程语言，而是一种**标记语言** (markup language)
- 它由一系列的**元素（elements）**组成，这些元素可以用来包围不同部分的内容
- 标记语言是一套**标记标签** (markup tag)
- HTML 使用**标记标签**来描述网页
- HTML的后缀名是 `.htm` 或 `.html`
- HTML是**由浏览器解释渲染**的语言


# 元素的分类
HTML（超文本标记语言）元素历来被归类为“块级”元素或者“行级”元素。

内联元素：默认情况下，相对父元素，元素不换行

块级元素：默认情况下，相对父元素，每个元素都会新起一行。（换行）



### 内联元素

在默认情况下**不**独占父元素一行的元素就是 **内联元素** ( inline element )。

常见的内联元素

- `span`
- `u` 表示下划线 
- `i` 表示斜体    
- `s` 表示删除线
- `b` 表示加粗
- `a` 表示 超链接 或 锚点
- <strong>： 表示强调文本，通常以粗体显示。
- <em>： 表示强调文本，通常以斜体显示。
- <abbr>： 表示缩写或首字母缩略词，可以通过title属性提供完整的解释。
- <code>： 用于表示计算机代码，通常以等宽字体显示。
- <cite>： 用于表示引用作品的标题，如书籍、文章等。
- <q>： 用于表示短的引用或内联引用文本，通常带有引号。
- <mark>： 用于标记文本的一部分，以进行突出显示。
- <br>： 用于创建换行，是唯一一个没有闭合标签的内联元素。
- <img>： 图像元素，用于在文档中嵌入图像。
- <input>： 输入元素，用于创建各种输入字段，如文本框、复选框、单选按钮等。
- <button>： 按钮元素，用于创建可点击的按钮。
- <label>： 用于为表单元素提供标签或说明。
- <select>： 用于创建下拉选择框。
- <textarea>： 用于创建多行文本输入框。
- <sub>： 下标元素，用于表示文本的下标。
- <sup>： 上标元素，用于表示文本的上标。
- <abbr>： 缩写元素，用于表示缩写或首字母缩略词。
- <time>： 用于表示日期和时间。
- <del>： 删除线元素，用于表示被删除的文本。
- <ins>： 插入线元素，用于表示插入的文本。



### 块元素

默认情况下，独自占用父元素一整行的元素就是 **块元素** ( block element )。

常用块元素:

- `p` 表示段落 ( paragraph )

- `div` 表示一个块

  - `div` 是 `division` 一词的缩写，表示用于划分不同区域

- `hn` 表示标题标记

  - h1 表示一级标题

  - h2 表示二级标题

  - h3 表示三级标题

  - h4 表示四级标题
  - h5 表示五级标题

  - h6 表示六级标题

- `hr` 表示水平线

- 列表

  - ul（unlist） 无序列表

  - ol（order list）  有序列表

  - dl（description list）描述列表
- <header>： <header> 元素通常用于定义页面或区域的页眉，可以包含标题、导航菜单等内容。
- <footer>： <footer> 元素通常用于定义页面或区域的页脚，可以包含版权信息、联系方式等内容。
- <nav>： <nav> 元素用于定义导航菜单，通常包含页面链接。
- <table>： 表格元素，用于创建表格结构。
- <tr>： 表格行元素，用于定义表格的行。
- <td>： 表格数据元素，用于定义表格中的单元格。
- <th>： 表格标题元素，通常用于定义表格的列标题。
- <article>：元素通常用于定义页面中的一篇文章或内容块。
- <section>：元素用于划分页面内容的不同部分。
- <aside>：通常用于定义与主要内容相关但可以被看作是独立的内容，如侧边栏、广告等。
- <figure>： 通常用于包含一些与文本相关的图像、图表、照片等。
- <figcaption>：用于定义 <figure> 元素的标题。
- <main>：用于定义页面的主要内容，一个页面中只应该有一个 <main> 元素。
- <form>：用于创建表单，通常包含输入字段、按钮等元素。
- <blockquote>：用于定义引用的块级内容，通常包含引用文本。


## HTML5  网页结构

```html
<!-- 文档声明  html5，简称 h5 -->
<!DOCTYPE html>
<html>
<head>
	<!-- 编码格式 -->
	<meta charset="utf-8">
	<!-- title 网页标题 -->
	<title>介绍html结构</title>
</head>
<body>
	网页内容
</body>
</html>
```



### 剖析HTML文档

1. `<!DOCTYPE html>`: 声明文档类型. 很久以前，早期的HTML(大约1991年2月)，文档类型声明类似于链接，规定了HTML页面必须遵从的良好规则，能自动检测错误和其他有用的东西(已过时)。现在这种声明方式是最短最有效的文档声明。

   ```html
   <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
   "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
   ```

2. `<html></html>`: `<html>`元素。这个元素包裹了整个完整的页面，是一个根元素。

3. `<head></head>`: `<head>元素`. 这个元素是一个容器，它包含了所有你想包含在HTML页面中但不想在HTML页面中显示的内容。这些内容包括你想在搜索结果中出现的关键字和页面描述，CSS样式，字符集声明等等。

4. `<meta charset="utf-8">`: 这个元素设置文档使用utf-8字符集编码，utf-8字符集包含了人类大部分的文字。基本上他能识别你放上去的所有文本内容。（以后都用这个）

5. `<title></title>`: 设置页面标题，出现在浏览器标签上，当你标记/收藏页面时它可用来描述页面。

6. `<body></body>`: 包含了你访问页面时所有显示在页面上的内容，文本，图片，音频，游戏等等。



### Head

HTML 头部是包含在 `<head>` 元素里面的内容。不像 `<body>`元素的内容会显示在浏览器中，`head` 里面的内容不会在浏览器中显示，它的作用是包含一些页面的`元数据`。

#### 增加一个标题

`<title>`标签可以用来给 `html` 文档添加一个标题。有可能会和 `body` 中添加标题的 `<h1>` 元素混淆，有些时候 h1 也会被称作网页标题。但是它们是不同的

- 当被加载到浏览器中的时候，元素 `<h1>`  会出现在页面中。来标记你的页面内容的标题
- 元素 `<title>` 是用来表示整个HTML文档标题的元数据（不是文档的内容）

#### 元数据：`<meta>`元素

元数据就是描述数据的数据，而HTML有一个“官方的”方式来为一个文档添加元数据——  `<meta>` 元素。

```html
<!-- 指定文档中字符的编码 -->
<meta charset="utf-8"/>
<!-- 添加作者和描述,作用是让你的页面在搜索引擎的相关的搜索出现 -->
<meta name="author" content="ycdl"/>
<meta name="keyword" content="itlb,java,关键字"/>
<meta name="description" content="itlaobing"/>
```

#### 增加自定义图标

```html
<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">
```

#### 在HTML中应用CSS和JavaScript

```html
<!-- rel="stylesheet"表明这是文档的样式表，而 href包含了样式表文件的路径 -->
<link rel="stylesheet" href="my-css-file.css">

<script src="my-js-file.js"></script>
```

> `script`部分没必要非要放在文档头部；实际上，把它放在文档的尾部（在 `</body>标签之前`）是一个更好的选择，这样可以确保在加载脚本之前浏览器已经解析了HTML内容（如果脚本加载某个不存在的元素，浏览器会报错）。



## 常见的标签

#### 列表

**有序列表**

```html
 <ol type="">
    <li> li 是 list item 的首字母缩写 </li>
    <li> li 表示列表项目(列表条目) </li>
 </ol>
```

> type="1" 数字风格表示列表顺序
>
> type="a" 小写字母风格表示列表顺序
>
> type="i" 罗马数字风格表示列表顺序



**无序列表**

```html
 <ul type="">
    <li> 无序列表 和 有序列表内部的 列表项目 都使用 li 元素来表示 </li>
    <li> 无序列表 和 有序列表内部的 列表项目 都使用 li 元素来表示 </li>
 </ul>
```

> type="disc" 实心圆表示列表顺序
>
> type="square" 矩形表示列表顺序
>
> type="circle" 空心圆表示列表顺序



**定义列表**

```html
<dl>
   <dt>标题</dt>
   <dd>对标题的描述</dd>
</dl>
```



#### 表格

表格由 <table> 标签来定义。

每个表格均有若干行（由 <tr> 标签定义），每行被分割为若干单元格（由 <td> 标签定义）。

例如：

```html
<table border="1" width="800px" >
    <!-- 表格标题 -->
    <thead>
        <tr>
            <th>1</th>
            <th>2</th>
            <th>3</th>
            <th>4</th>
        </tr>
    </thead>
    <!-- 表格主体 -->
    <tbody class="foot">
        <tr>
            <td>3</td>
            <td>3</td>
            <td>3</td>
            <td>3</td>
        </tr>
    </tbody>
</table>
```

`table`可以有如下属性：

- `border`  表格边框
- `cellspacing` 单元格之间的空间
- `cellpadding` 单元格填充
- `width` 表格宽度



**表格标签**

| 表格      | 描述             |
| :-------- | :--------------- |
| <table>   | 定义表格         |
| <caption> | 定义表格标题。   |
| <th>      | 定义表格的表头。 |
| <tr>      | 定义表格的行。   |
| <td>      | 定义表格单元。   |
| <thead>   | 定义表格的页眉。 |
| <tbody>   | 定义表格的主体。 |
| <tfoot>   | 定义表格的页脚。 |

> rowspan  合并行  colspan 合并列



#### 表单

form表单：`<form>` 用于为用户输入创建 HTML 表单，是数据传输的载体

```html
<form name="表单名称" method="表单提交方式" action="规定当提交表单时向何处发送表单数据"></form>
```

表单元素

| 标签       | 作用                                     |
| :--------- | :--------------------------------------- |
| <input>    | 根据 type 属性值的不同，表示多种输入形式 |
| <textarea> | 表示多行文本框                           |
| <select>   | 表示下拉框，下列框的条目用<option>表示   |
| <button>   | 表示按钮                                 |

#### 超链接

```html
<a href="" target="_blank" ></a>
```

href:不能缺省 

| <a href="https://www.baidu.com" >百度一下</a> |
| --------------------------------------------- |
| Target属性:                                   |
| _blank     在新的标签页里打开链接             |
| _parent    在父页面中打开链接                 |
| _self       在本页面打开链接                  |
| _top       最顶级页面打开链接                 |

**锚链接**

通过`a`标签的`name`或者`id`属性设置锚点，然后通过`href`属性进行跳转(`#`+ 锚点名称)

```html
<a href="javascript:void(0)">xxx</a>不跳转
<a href="#">xxx</a>定义为锚
```

**下载资源**

```html
<a href="../../other/zjmnk.m4a" download> 下载mp3 </a>
```

> 同源协议才生效【协议相同，域名相同，端口相同】

**邮件**

```html
<a href="mailto:xxxxx@qq.com"> 发送邮件 </a>
```

**电话**

```html
<a href="tel:xxxx"> 电话 </a>
```

> 根据设备决定行为【手机拨号，电脑跳转到拨号页面】

#### 多媒体

`<img>` 标签向网页中嵌入一幅图像。

```html
<img src=""/>
```

- `src`:图片的地址,可以是相对/绝对路径，也可以是`Base64`码

- `alt`图片不能正常显示时，显示此属性的值

- `title`鼠标悬停时,出现的文字（这个属性也可以在其他元素上使用）
- `width/height` 宽度/高度，可以设置百分比、数值。但是通常不建议同时设置这两个属性



`<audio></audio>` 标签定义声音，比如音乐或其他音频流。

`<video></video>` 标签定义视频，比如电影片段或其他视频流。

```html
<img src="ayao.jpg">
<audio src="LastWillandTestamentD.mp3" autoplay="autoplay" controls="controls" ></audio>
<video src="阆中之恋.mp4" autoplay="autoplay" controls="controls" muted="muted"></video>
```

> 必须有 src 属性



#### H5新增标签

- `<datalist>`定义下拉列表用法如下   

  ```html
  <input id="myCar"  list="cars" />   
  <datalist id="cars">      
      <option value="BMW">       
      <option value="Ford">       
      <option value="Volvo">   
  </datalist> 
  ```

- `<embed>` 标签定义嵌入的内容，比如插件。       

  ```html
  <embed src="helloworld.swf"   /> 
  ```

- `<nav> `导航 在H4中导航栏一般用ul-li标签，H5中可以直接用`<nav>`标签

- `<figure>`和` <figcaption>`：`<figure>`为父元素，用于图片的外层，其子元素

- `<figcaption>`用来对内容进行说明。

- `<hgroup>` 页面上得一个标题组合（一个标题和一个子标题）       

- `<details>` 标签，用于描述文档或文档某个部分的细节。与`<summary>`标签配合使用可以为 `details`定义标题。标题是可见的，用户点击标题时，会显示出 `details`。 

- `<mark>` 标签，定义带有记号的文本。在需要突出显示文本时使用 该 标签，默认加黄色背景 

- `reversed`属性:`<ol>`的属性，定义序号是否倒叙   `start`属性：`<ol>`的属性，定义序号的起始值 

- `<marquee>`滚动文字                                          

具体见：[HTML 参考手册- 菜鸟教程](https://www.runoob.com/tags/html-reference.html)

[MDN-HTML](https://developer.mozilla.org/zh-CN/docs/Web/HTML)

