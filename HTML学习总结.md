# HTML学习总结

## 0. 何为HTML

HTML是超文本标记语言（HyperText Markup Language）的缩写。我们用HTML来构建web即所谓的网页。

<table><tr><td bgcolor=F6E6FA>Hypertext是指链接单个网站内或多个网站间的网页的链接。 链接是网络的一个基本方面。</td></tr></table>

    <font color=#0099ff size=4 ><strong>HTML</strong></font> 定义了网页内容的含义和结构。除了HTML以外的其他技术通常用来描述一个网页的表现与展示效果(CSS)，或者功能与行为(JavaScript)。

<font color=#0099ff size=4 >**HTML**</font> 是一种用于定义内容结构的**标记语言**而非编程语言，任何一个网页背后都是一个HTML文档，在网页中按<kbd>**F12**</kbd>即可查看源代码。

<table><tr><td bgcolor=F6E6FA>HTML ,CSS(Cascading Style Sheets 级联式样式表),JavaScript是构架Web程序的三要素。


## 1. HTML文档结构

搭建工作环境：VScode[^1]以及相关插件的安装[code下载](https://code.visualstudio.com/)。

创建自己第一个**HTML**文档：

* 运行VScode，新建一个文件夹[^2],同时打开自动保存，避免工作时程序崩坏文件丢失。
* 创建一个后缀名为html的文件，输入以下内容查看结果：

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <link rel="shortcut icon" href="favicon.ico" type="image/x-icon">
  <title>页面标题</title>
</head>
<body>
  <h1>我的第一个Web页</h1>
  <p>当前有点丑：)</p>
</body>
</html>
```

* 右键html文件，选择用游览器打开[^3]展示结果如下：

<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <link rel="shortcut icon" href="favicon.ico" type="image/x-icon">
  <title>页面标题</title>
</head>
<body>
  <h1>我的第一个Web页</h1>
  <p>当前有点丑：)</p>
</body>
</html>



### 1.1文档结构分析

<font color=#0099ff size=4 >**HTML元素**</font>：HTML使用标记来注明文本，图片和其他内容，以便于在游览器中显示。HTML中包含了很多规定的元素，如`<head>` ,`<titale>`, `<body>`等，它们可以嵌套，同时元素又由一对标签(tag)组成，并且都遵循这这样一个书写格式：

![语法结构](https://qige.io/web/brief-html/img/f63738cc51ebfa14.png)

* **开始标签**（Opening tag）：包含元素名称，被角括号包围。表示元素从这里开始起作用。
* **结束标签**（Closing tag）：包含元素名称，被角括号包围。表示元素从这里结束[^4]。
* **内容**（Content）：元素内容，本例时所输入的文本本身。
* **元素**（Element）：由以上三种元素组成。

***

<font color=#0099ff size=4 >**HTML文档**</font>：针对前面所创建的HTML文档，结构剖析如下：

1. `<!DOCTYPE html>`：声明文档类型。现在已经可有可无。
2. `<html></html>`：此元素包裹了整个完整页面，是一个根元素，**其他元素都嵌套在其中**。
3. `<head></head>`：此元素是一个**容器**，它包含了所有你想包含在HTML页面中但不想直接显示在主页面的内容。这些内容包含了你想在**搜索结果**中出现的**关键字**和**页面描述**，**css样式**，字符集声明等等。
4. `<meta charset="utf-8">`：这个元素设置了文档使用UTF8编码，基本上能识别你放上去的所有文本内容，通常直接默认使用它。
5. `<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">`：指定页面图标[^5]，出现在游览器标签上。
6. `<title></title>`：设置页面标题，出现在游览器标签和收藏夹中。
7. `<body></body>`：此元素包含了你能在页面中看到的所有内容，包括文本，图片，音频，游戏等等。

<table><tr><td bgcolor=F6E6FA>注意：HTML不区分标签大小写，但建议全部使用小写。

### 1.2文档相关说明

<font color=#0099ff size=4 >**注释**</font>：和大部分编程语言一致在HTML中有一种可用的机制在代码中书写注释。注释在客户端是被忽略对用户不可见的，只对后台开放。

为了将一段HTML中的内容置为注释，需要用`<!--` ,`-->`把它包裹起来，比如：

```html
<p>注释外可显示的文本内容</p>
<!--<p>注释内不可显示的文本内容</p>-->
```

此内容过于简单不再展示。

<table><tr><td bgcolor=F6E6FA>提示：在code软件中输入Ctrl+/即可快捷注释。

<font color=#0099ff size=4 >**空元素**</font>：元素一般都由开始标签，结束标签形成头尾。但有一些元素只有一个开始标签，如：`<br>`, `<hr>` `<input>` `<img>` `<a>`等等，我们称其为空元素，一般用来在元素所在位置插入/嵌套一些东西。

<font color=#0099ff size=4 >**元素的属性**</font>：元素是有相关属性的。属性包含元素的额外信息，这些信息不对外显示。

```html
<!-- 带属性的段落输入框 -->
<p title="这是个title属性">鼠标移上来试试！</p>
<!-- 带属性的输入框 -->
<input type="text">
<input type="password">
```

**一个属性必须包含以下内容**：

* 一个空格，在属性和元素名称之间[^6]。
* 属性名称，后面跟着一个`=`号。
* 一个属性值，由一对引号引起来。

## 2. HTML基础语法

### 2.1 标题

HTML和markdown一样提供了从大到小6级标题，`<h1> ~ <h6>`。

在页面中标题非常重要：

* 搜索引擎通过标题来索引页面内容
* 用户也习惯依赖标题来进行主要内容浏览**（标题党）**

`（内容过于简单不予展示）`

<table><tr><td bgcolor=F6E6FA>小贴士：h1最醒目，通常用于主标题，但设计页面的同时不应为了醒目而盲目加粗或者放大。

***

### 2.2 文本格式

本次课程我们需要知道的**文本格式**标签如下：

| \<mark>                | <mark>高亮文本</mark>                                        |
| ---------------------- | ------------------------------------------------------------ |
| **\<del>**             | <del>划掉文本</del>                                          |
| **\<s>**               | 同上，通常用<del>代替                                        |
| **\<ins>**             | <ins>标签定义已经被插入文档中的文本（推荐于del一起使用）</ins> |
| **\<u>**               | <u>标签可定义下划线文本</u>                                  |
| **\<small>**           | <small>字体变小</small>                                      |
| **\<strong>**/**\<b>** | <strong>字体加粗</strong>                                    |
| **\<em>**/**\<i>**     | <em>字体变斜</em>                                            |

***

### 2.3 超链接 a

<font color=#0099ff size=4 >**超链接语法**</font>：

```html
<a href="https://www.baidu.com/" target="_blank">澳门赌场入口</a>
```

成分剖析：

* `href`：即为要跳转去的网址URL。
* `target`：属性为`_blank`表示在新的页面打开超链接（默认是在当前页面打开`_self`）。
* 超链接标签包含的内容（可以是图片）即为客户端所呈现的供点击内容。

效果展示：

<a href="https://www.baidu.com/" target="_blank">澳门赌场入口</a>



<font color=#0099ff size=4 >**锚点**</font>：锚点也称为书签，用于标记页面的某个元素的位置，通过锚点实现长页面内部跳转。

使用方法：通过**`id`**属性生成锚点，然后再用超链接指向该锚点即可：

```html
<!-- 文档其余部分 -->
<h2 id="C4">塑胶炸药</h2>
<!-- 文档其余部分 -->
<a href="#C4">转至塑胶炸药所在地</a>
<!-- 文档其余部分 -->
```

效果展示[^7]：


<h6 id="C4">塑胶炸药</h6>

>
>
>
>
>
>
>

<a href="#C4">转至塑胶炸药所在地</a>

<table><tr><td bgcolor=F6E6FA>注意：元素id的值唯一；并且href所指向的锚点id前要有#。

***

### 2.4 图片及文件路径 img

<font color=#0099ff size=4 >**图片**</font>：

在页面插入一张图片语法如下：

```html
<img src="https://static3.srcdn.com/wordpress/wp-content/uploads/2019/02/Apex-Legends-Trailer-Gameplay-Details.jpg" alt="ApexGirls" <!--/*width="200" height="200"-->>
```

效果展示[^7]：

<img src="https://static3.srcdn.com/wordpress/wp-content/uploads/2019/02/Apex-Legends-Trailer-Gameplay-Details.jpg" alt="ApexGirls">

元素剖析：

* `src`属性表示要显示图片文件的位置URL/路径。
* `alt`属性表示当获取图片出错时显示的文字（占位符）。
* 可为图片指定尺寸，但不建议（可能导致图片变形）。

<table><tr><td bgcolor=F6E6FA>注意：对于小尺寸的图片，可以采用<a href="https://c.runoob.com/front-end/59" target="_blank">Base64转码</a>方法来提高页面加载速度，以此来提高用户体验。对于大尺寸图片可以使用<a href="https://www.websiteplanet.com/zh-hans/webtools/imagecompressor/" target="_blank">WebsitePlanet</a>或<a href="https://tinify.cn/" target="_blank">TinyPNG(CN)</a>等压缩工具来解决图片加载速度过慢的问题。

<font color=#0099ff size=4 >**文件路径**</font>：

文件路径表示文件的位置，共有相对路径和绝对路径两种。

绝对路径不再解释，下面请看相对路径的典例：

| 例子                               | 解释                               |
| ---------------------------------- | ---------------------------------- |
| `<img src="picture.jpg">`          | 图片文件与当前文档在同一目录中     |
| `<img src="./images/picture.jpg">` | 图片文件在当前目录下的images目录中 |
| `<img src="../picture.jpg">`       | 该图片文件在上一级目录中           |

**拓展：图片超链接** 将\<a href=XXX>\</a>中的文本元素换成图片元素即可。

### 2.5 表 Table/List/Form

<font color=#0099ff size=4 >**表格 Table**</font>：

当页面中的内容需要表格来整理时，我们选择使用`<table></table>`标签即可。

```html
  <table>
    <tr>
      <th>👴是表头</th>
      <th>第二个表头</th>
      <th>👴👴👴👴👴</th>
    </tr>
    <tr>
      <td>我是第一列第一个元素</td>
      <td>母猪的产后护理</td>
      <td>你看下面的元素缺失了</td>
    </tr>
    <tr>
      <td>尼古拉斯</td>
      <td align="right">向右对齐</td>
    </tr>
  </table>
```

以上代码效果如下[^7]：

  <table>
    <tr>
      <th>👴是表头</th>
      <th>第二个表头</th>
      <th>👴👴👴👴👴</th>
    </tr>
    <tr>
      <td>我是第一列第一个元素</td>
      <td>母🐖🐖的产后护理</td>
      <td>你看下面的元素缺失了</td>
    </tr>
    <tr>
      <td>尼古拉斯</td>
      <td align="right">向右对齐</td>
    </tr>
  </table>

元素剖析：`<tr>`表示行，`<td>`表示行中的单元，`<th>`表示的是表头的单元。由上图可知缺失元素时表格会向左对齐。

<font color=#0099ff size=4 >**列表 List**</font>：

HTML的列表和markdown一样分为有序列表和无序列表，显示效果基本一致。

1. 无序列表：

   ```html
   <ul>
     <li>👴我是爷爷</li>
   </ul>
   <ul type="square">
     <li>👵我是奶奶</li>
       <ul type="circle">
     <li>👶俺是孙ze</li>
   </ul>
   ```

   代码效果如下：

   <ul>
     <li>👴我是爷爷</li>
   </ul>
     <ul type="square">
     <li>👵我是奶奶</li>
         <ul type="circle">
     <li>👶俺是孙ze</li>
   </ul>

   **元素剖析：**

   无序列表使用`<ul>`标签，默认使用圆点[^8]作为前标，另外还有方块，实心圆等标志，如上图所示；同样可以嵌套。

2. 有序列表：

   ```html
   <ol>
     <li>有序列表使用<kbd>ol</kbd>标签</li>
     <li>它默认以数字作为每项标志，其他的标志可以是大小写字母或是罗马字母i</li>
   </ol>
   <ol type="a">
     <li>我是小写字母a</li>
     <li>我是小写字母b</li>
   </ol>
   <ol type="i">
     <li>我是罗马编号i</li>
     <li>我是罗马编号ii</li>
   </ol>
   ```

   代码效果如下：
   <ol>
     <li>有序列表使用<kbd>ol</kbd>标签</li>
     <li>它默认以数字作为每项标志，其他的标志可以是大小写字母或是罗马字母i等</li>
   </ol>
   <ol type="a">
     <li>我是小写字母a</li>
     <li>我是小写字母b</li>
   </ol>
   <ol type="i">
     <li>我是罗马编号i</li>
     <li>我是罗马编号ii</li>
   </ol>

<font color=#0099ff size=4 >**表单 Form**</font>：

当网站需要获取我们的一些信息如：账户，选择，意见等，我们就需要使用表单来让用户进行填写或选择。

1. **文本输入框**，常用于输入包含字符字母文字的字符串内容，比如用户名和密码。

```html
<form>
  <!-- 文本框，注意有 placeholder 提示符 -->
  用户名：<br>
  <input type="text" name="name" placeholder="请输入用户名"><br>
  <!-- 密码框 -->
  密码：<br>
  <input type="password" name="ps" placeholder="这里是未被访问时所展示内容"><br>
</form>
```

<form>
  <!-- 文本框，注意有 placeholder 提示符 -->
  用户名：<br>
  <input type="text" name="name" placeholder="请输入用户名"><br>
  <!-- 密码框 -->
  密码：<br>
  <input type="password" name="ps" placeholder="这是未被访问时所示内容"><br>
</form>

***

2. **数字输入框**，可设置取值范围，注意`value`属性为默认值：

```html
年龄：<br>
  <!-- 数字输入框，注意 min 和 value 属性-->
  <input type="number" name="age" min="18" value="18"><br>
```

<form>
    年龄：<br>
  <!-- 数字输入框，注意 min 和 value 属性-->
  <input type="number" name="age" min="18" value="18"><br>
</form>

***

3. **单选列表**，`checked`属性代表默认点击。

```html
<form>
  <!-- 单选按钮, 注意 checked 属性 -->
  性别：<br>
  <input type="radio" name="gender" value="male" checked> 男<br>
  <input type="radio" name="gender" value="female"> 女<br>
  <input type="radio" name="gender" value="other"> 这里的type表示选项按钮外观<br>
</form>
```

<form>
  <!-- 单选按钮, 注意 checked 属性 -->
  性别：<br>
  <input type="radio" name="gender" value="male" checked> 男<br>
  <input type="radio" name="gender" value="female"> 女<br>
  <input type="radio" name="gender" value="other"> 这里的type表示选项按钮外观<br>
</form>

***

4. **下拉列表**，注意`selected`属性表示默认选择内容。

```html
<form>
     <!-- 下拉列表，注意 selected 属性 -->
  党派：<br>
  <select name="party">
    <option value="D">民主党</option>
    <option value="R" selected>共和党</option>
    <option value="N">无党派</option>
  </select><br>
</form>
```

<form>
     <!-- 下拉列表，注意 selected 属性 -->
  党派：<br>
  <select name="party">
    <option value="D">民主党</option>
    <option value="R" selected>共和党</option>
    <option value="N">无党派</option>
  </select><br>
</form>

***

5. **多选框**，注意`checked`属性与单选列表相同。

```html
<form>
  <!-- 多选框 -->
  您有哪些交通工具：<br>
  <input type="checkbox" name="vehicle1" value="Bike"> 自行车<br>
  <input type="checkbox" name="vehicle2" value="Motocycle" checked> 摩托车<br>
  <input type="checkbox" name="vehicle3" value="Car"> 轿车<br>
  <input type="checkbox" name="vehicle4" value="Jet"> 这里的type表示选项按钮外观<br>
</form>
```

<form>
  <!-- 多选框 -->
  您有哪些交通工具：<br>
  <input type="checkbox" name="vehicle1" value="Bike"> 自行车<br>
  <input type="checkbox" name="vehicle2" value="Motocycle" checked> 摩托车<br>
  <input type="checkbox" name="vehicle3" value="Car"> 轿车<br>
  <input type="checkbox" name="vehicle4" value="Jet"> 这里的type表示选项按钮外观<br>
</form>

***

6. **日期选择器**：

```html
<form>
  <!-- 日期选择器 -->
  点击选择日期：<br>
  <input type="date"><br>
</form>
```

<form>
  <!-- 日期选择器 -->
  点击选择日期：<br>
  <input type="date"><br>
</form>

***

7. **文件选择器**

```html
<form>
  <!-- 文件选择器 -->
  上传您的文件:<br>
  <input type="file" name="Files"><br>
</form>
```

<form>
  <!-- 文件选择器 -->
  上传您的文件:<br>
  <input type="file" name="Files"><br>
</form>

***

8. **文本输入框**，`rows`与`cols`分别表示行数和每行最大字数。

```html
<form>
  <!-- 文本输入区域，注意 rows 和 cols 属性 -->
  您的建议：<br>
  <textarea name="message" rows="5" cols="30">
    这是默认展示的文本内容。
  </textarea><br><hr>
</form>
```

<form>
  <!-- 文本输入区域，注意 rows 和 cols 属性 -->
  您的建议：<br>
  <textarea name="message" rows="5" cols="30">
    这是默认展示的文本内容。
  </textarea><br><hr>
</form>



9. **按钮**：与用户互动的主力军之一。

```html
<form>
  <!-- 表单提交/重置按钮，将表单中的数据取消或传输给服务器端进行处理 -->
  <input type="submit" value="提 交">
  <input type="reset" value="重 置">
</form>
```

<form>
  <!-- 表单提交/重置按钮，将表单中的数据取消或传输给服务器端进行处理 -->
  <input type="submit" value="提 交">
  <input type="reset" value="重 置">
</form>

***

### 2.6 其他

HTML 的元素可以称为**区块**或**内联**的方式进行显示：

<font color=#0099ff size=4 >**区块元素**</font>：

区块元素在游览器显示时通常会以**<mark>新行</mark>**来开始和结束，比如：`<h1>,<pre>,<ul><table><div>`等。

<small>内容过于简单不予展示。</small>

***

<font color=#0099ff size=4 >**内联元素**</font>：

内联元素相反，他们总是一个接一个进行显示，不会新起一行。如： `<span>, <input>, <td>, <a>, <img>`等。

<small>内容过于简单不予展示。</small>

***

<font color=#0099ff size=4 >**预设格式**</font>：

如果想要网页内容展示直接使用HTML文档内格式的文本内容可以使用`<pre>`标签。但它不可以用于在页面内直接展示HTML源代码。

<small>内容过于简单不予展示。</small>

***

<font color=#0099ff size=4 >**特殊字符**</font>：

`<pre>`标签不能用于在页面内直接展示HTML源代码，同样，在HTML中有很多字符被用于语法，导致了很多字符不能直接拿来当作文本内容。

比如，你想直接在页面中展示下一段源代码：

```html
<pre>
<h1>这是个一级标题</h1>
<p>有多   远，滚      多远！</p>
  <p>这是一个段落<p>
  <a href="https://twitter.com/">眼见何事，情系何处，身处何方，心思何人</a>
  </pre>
```

可得到的结果是这样的：

<pre>
<h1>这是个一级标题</h1>
<p>有多   远，滚      多远！</p>
  <p>这是一个段落<p>
  <a href="https://twitter.com/">眼见何事，情系何处，身处何方，心思何人</a>
  </pre>

对于初学者来说是不按套路出牌的，你很失望，超链接还是出现了，于是乎在查阅<a href="https://www.runoob.com/tags/ref-entities.html">ISO-8859-1 字符实体手册</a>后，你找到了代替特殊字符的代码，给出了下面的结果：

```html
<p>有多&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;远，滚&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;多远！</p>
<hr>
<h2>test.html</h2>
<pre>
  &lt;h1&gt;这是个一级标题&lt;/h1&gt;
  &lt;p&gt;这是一个段落&lt;p&gt;
  &lt;a href="https://twitter.com/"&gt;眼见何事，情系何处，身处何方，心思何人&lt;/a&gt;
<pre>
```

<p>有多&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;远，滚&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;多远！</p>
<hr>
<h2>test.html</h2>
<pre>
  &lt;h1&gt;这是个一级标题&lt;/h1&gt;
  &lt;p&gt;这是一个段落&lt;p&gt;
  &lt;a href="https://twitter.com/"&gt;眼见何事，情系何处，身处何方，心思何人&lt;/a&gt;
<pre>


正确结果出现了，你很欣慰，因为这篇笔记终于<mark>结束</mark>了。

***

### 2.7 错题库

<font color=#0099ff size=4 >**作业错题**</font>：

* **\<input type="text">** 用于产生文本框
* **\<textarea>** 用于产生文本区
* **\<body background="background.gif">** 用于插入背景图像
* **HTML**与**XML **的区别在于HTML不要求标记的嵌套，配对等，不要求标记间具有一定的顺序，而**XML**则是**严格要求嵌套，配对**。
* **DOM** 代表文档对象模型
* **DTD** 代表文档类型定义
* **\<div>** 标签的作用在于按逻辑划分页面文档
* **\<meta>** 标签的作用在于储存与游览器和搜索引擎相关的信息
* 对 于HTML 中的框架(iframe、frameset)，**使用** <kbd>*</kbd>指定屏幕的其余部分
* 当前文档和链接文档之间的关系是使用 **\<rel>** 属性指定的
* **\<target>** 的默认属性是在当前页面打开`_self`
* 浏览器中未访问链接的默认样式和颜色为**下划线+蓝色**
* 如果我们需要发送电子邮件，那么锚链接的 href 属性以**mailto**关键字开始
* **\<area>** 标记用于定义图像映射中的可单击区域
* **万维网**的标记语言**一直是 HTML**
* 如果背景图像比屏幕小，它会重复

***









[^1]: 这里推荐VScode，免费方便快捷。
[^2]: 不建议放在C盘，如果非要放在C盘，请放在Windows用户文档内。
[^3]: 这里需要open in browser插件，并推荐使用Chrome，edge，火狐游览器。
[^4]: 初学者经常忘记书写结束标签。
[^5]: 图标文件后缀名是**.ico**。
[^6]: 如果已经有一个或多个属性，就与前一个属性之间留一个空格。
[^7]: Markdown可支持多种html元素在md文件中直接显示。
[^8]: 默认是实心圆点，不知为何这里展示的是空心圆。