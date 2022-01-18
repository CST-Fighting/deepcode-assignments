## html

#### 基础知识

文件的基本结构

1）标签

<元素名称>要控制的元素</元素名称>

首标签语法：<元素名称 属性1=“值1” 属性2 = “值2”....>

尾标签：</元素名称>

2）文件结构

```
<!DOCTYPE html>   #注释
<html lang="en">      #文件开始
<head>     #文件头
    <meta charset="UTF-8">
    <title>文件标题</title>    #文件标题
</head>      #文件头

<body>    #文件主体

</body>    #文件主体
<div id ="box">
    <div></div>

</html>    #文件结束
```

***



#### 分区div

###### 1）<div>标签是用来为HTML文档的内容提供结构和背景的元素。

```
#语法：
<div>
...
</div>
```

###### 2）<div>标签的应用

```
#语法：
<div id="value" align="value" style="value">
</div>
#id:<div>标签的id也可以说是他的名字，常与css样式相结合，实现对网页中的元素的控制
#align：用于控制<div>标签中的元素的对齐方式。
#class：设置<div>标签中的元素的样式，其值为css样式中的class选择符。
#style：设置<div>标签中的元素的样式，其值为css的属性值，各属性之间使用分号分隔。
```

```
#<span>标签，与<div>类似
#语法：
<span>
...
</span>
#<span>标签，为行内标签，可以作为插入css这类风格的容器，或者插入class、id等语法内容的容器。他前后不会换行，没有结构意义，纯粹是为了应用样式。当其他行内元素都不适合的时候，就使用<span>标签。
```

***



#### 标题h1~h6

###### 1）标题标签

```
#<h1>到<h6>字体大小一次变小
<h1>文本内容</h1>
<h2>文本内容</h2>
<h3>文本内容</h3>
<h4>文本内容</h4>
<h5>文本内容</h5>
<h6>文本内容</h6>
```

###### 2）标题的对齐方式【left,right,center】

默认情况下为，左对齐

可以为标题标签添加align属性进行设置

```
语法：<h1 align="对齐方式">文本内容</h1>
```

***



#### 段落p

段落效果是通过<p>标签来实现的。<p>会自动子啊其前后创建一些空白，浏览器会自动添加这些空间

```
语法：<p>段落文字</p>
```

段落的换行标签：

```
<p>
一段文字<br/>一段文字    #<br/>标签代表换行
</p>
```

段落的原始排版标签

```
<pre>
文本内容
</pre>
```

***



#### 图像img

##### 添加图像

基本格式：GIF、JPEG、PNG

```
添加图像的方法：<img src="图像文件的地址">    #相对地址，也可以是绝对路径
```

##### 设置图像属性

###### 图像大小与边框

1）调整图像大小【若高度/宽度只设置一个，那么另一个参数就会按照相同的比例进行调整】

```
<img src="图像文件的地址" height="" width="">   #height用于设置图像的高度，单位为像素，                                         可省; width用于设置图像的宽度，单位为像素，可省
```

2）设置图像边框---border,单位为像素

```
<img src="图像文件的地址" border="">  
```

3）图像间距与对齐方式

调整间距：

hspace：图像水平间距

vspace：图像垂直间距

``` 
<img src="图像文件的地址" hspace="" vspace="">  
```

设置图像相对于文字基准线的对齐方式

```
<img src="图像文件的地址" align="相对文字的对齐方式">

#其中align的取值
top          图像的顶部和同行的最高部分对齐
middle       图像的中部和同行的中部对齐
bottom       图像的底部和同行文本的底部对齐
absmiddle    图像的中部和同行中最大项的中部对齐
baseline     图像的底部和同行中的基线对齐
absbottom    图像的底部和同行中的最低项对齐
left         使图像和左边界对齐（文本环绕图像）
right        使图像和右边界对齐（文本环绕图像）
```

###### 提示文字与替换文本【中英文皆可】

1）添加图像的提示文字---title

```
<img src="图像文件的地址" title="">  #title后面的双引号的内容就是图像的提示文字
```

2）添加图像的替换文本----alt

```
<img src="图像文件的地址" alt="">  #alt后的双引号内容为图像的替换文本
```



***





#### 列表ul / ol

##### 列表标签：有序列表（ol）、无序列表(ul)

##### 无序列表     

1）【特征：提供一种不编号的列表方式，而在每个项目文字之间以符号作为分项标识】

```
<ul>
    <li>第1项</li>       #<li>标签表示一个列表项的开始
    <li>第2项</li>
</ul>
```

2）无序列表的属性

- 默认情况下，无序列表的项目符号为一个小黑点,即disc。但用了type可以调整无序列表的项目符号【type取值disc,circle,square】

```
#语法：
<ul type=符号类型>
    <li>第1项</li>       
    <li>第2项</li>
    ...
</ul>
```

也可以在<li>标签中，其语法为：

```
<li type=符号类型>
```

若不需要无序列表的项目符号，则只需将无序列表的列表项目的序号类型设置为none即可，也可将list-style属性设置为none。



##### 有序列表

1）有序列表的标签，主要使用<ol>和<li>，以及type和start两个属性

```
#默认情况下，采用数字序号进行排列，语法如下:
<ol>
   <li>第1项</li>
   <li>第2项</li>
   ...
</ol>
```

2）属性

通过type可以调整序号的类型，例如：

```
<ol type=序号类型>
     <li>第1项</li>
     <li>第2项</li>
     <li>第3项</li>
     ...
</ol>
```

```
#type的取值                         列表项目的序号类型
1                                   数字1，2，3，...
a                                   小写英文字母a,b,c...
A                                   大写字母A,B,C...
i                                   小写罗马数字i,ii,iii,iv...
I                                   大写罗马数字I,II,III,IV...

```

##### 列表的嵌套

【定义列表是一种含有两个层次的列表，用于解释名词的定义，名词为第一层次，解释为第二层次，并且不包含项目符号】

```
<dl>
   <dt>名词1</dt>
<dd>解释1</dd>      #一个<dt>标签下可以有多个<dd>标签作为名词的解释和说明
<dd>解释2</dd>
<dd>解释3</dd>
   <dt>名词2</dt>
<dd>解释1</dd>
<dd>解释2</dd>
<dd>解释3</dd>
...
</dl>
```

##### 无序列表和有序列表的嵌套

【可以重复使用<ol>和<ul>标签组合】

***



#### 超链接a

###### 1）整幅图像的超链接

```
<a href="链接地址" target="目标窗口的打开方式"><img src="图像文件的地址"></a>  
#可以在图像属性中添加图像的其他参数，如height、border、hspace.
```

###### 2）图像热区链接

```
#1.在图像文件中设置映射图像名。在添加图像<img>标签中使用usemap属性添加图像要引用的映射图像的名称，语法：
<map src="图像地址" usemap="映射图像名称">
#2.定义热区图像的名称，语法：
<map name="映射图像名称">
   <area shape="热区形状" coords="热区坐标" href="链接地址" />
</map>
```

```
shape【用来定义热区的形状】的取值为rect(矩形区域)、circle(圆形区域)、ploy(多边形区域)
coord【用来设置区域坐标】对于矩形区域的取值left、top、right、bottom
     对于原型区域的取值center-x、center-y、tadius，也可以看作圆形的圆心坐标(x,y)与半径的值
     对于多边形区域，设置坐标参数比较复杂，所以coords参数需要按照顺序（逆时针/顺时针）取各个坐      标值。
```

***





#### 表单form

##### 表单概述

1）表单标签<form>

在表单的<form>标签中，还可以设置表单的基本属性，包括表单的名称、处理程序、传送方式等，语法：

```
<form action="" name="" method="" enctype="" target="">
...
</form>
```

```
action,表单的处理程序，就是表单中收集到的资料将要提交的程序地址，该地址可以是绝对/相对/其他地址，如：E-mail地址等
name，表单的名称，尽量与表单的功能相符，名称中不含空格、特殊符号
method，定义处理程序从表单中获取信息的方式，有get（默认值）,post两个值
enctype,表单信息提交的编码方式。其属性值有text/plain,application/x-www-form-urlencoded,multipart/form-data三个
target，目标窗口的打开方式，属性和含义与链接标签中的target相同
```

##### 输入标签

###### 文本框【分为单行文本和密码文本输入框，不同的文本框对应的type属性、表现形式和应用不同】

- 单行文本框

```
#语法：
<input type="text" name="" size="" maxlength="" value="">

#text属性用来设定表单的文本框中输入任何类型的文本、数字、字母。输入的内容以单行显示。
#name,文本框的名称，用于和页面中的其他控件加以区别。命名时不能包含特殊字符，也不能以HTML预留字作为名称
#size，定义文本框在页面中显示的长度，以字符作为单位
#maxlength,定义在文本框中最多可以输入的文字数
#value，用于定义文本框中的默认值
```

- 密码输入框

输入文本域的文字均以”*“或者圆点显示，语法如下：

```
<input type="password" name="" size="" maxlength="" value=""/>
```

###### 单选按钮和复选框

【常用于问卷调察和在购物车中结算商品等。单选按钮实现在一组选项中只选择其中一个，复选按钮，可实现多选/全选】

- 单选按钮

单选按钮用来让浏览者在答案之间进行单元选择

```
<input type="radio" value="单选按钮的取值" name="单选按钮的名称" checked="checked" />
```

```
value，设置用户选中该项目后，传送到处理程序中的值

name，单选按钮的名称。在一组单选按钮中一般其名称相同，这样在传递时才能更好的 对某个选择的内容的取值进行判断

checked，表示这一单选按钮默认被选中。在一组单选按钮中只能只有一项单选按钮被设置为checked。
```



- 复选按钮

```
<input type="checkbox" value="复选框的取值" name="名称" checked="checked" />
```

其中，checked=“checked”可以简写为”checked“。



###### 按钮【分为普通按钮、提交按钮、重置按钮】

- 普通按钮【一般配合JavaScript用】

```
<input type="button" value="按钮的取值" name="按钮名" onclick="处理程序" />
#value，按键上显示的文字
#name，按钮的名称
#onclick,当单击按钮时所进行的处理
```

- 提交按钮

【无需onclick属性，单击该按钮即可】

```
<input type="submmit" name="按钮名" value="按钮的取值"/>
#当提交按钮没有设置按钮取值时，就默认取值为“提交”。
```

- 重置按钮

【可清除表单的内容，回复默认的表单内容设定】

```
<input type="reset" name="按钮名" value="按钮的取值" />
#当重置按钮没有设置按钮取值时，就默认取值为“重置”。
```



##### 图像域和文件域

###### 1）图像域

```
<input type="image" src="" name=""/>
#src,设置图片地址，绝对/相对地址都可
#name，设置所要代表的按键，如submit、button等，默认值为button。
```

###### 2）文件域

```
<input type="file" accept="" name="">
#accept,所接受的文件类型
#name，文件传输的名称，用于和页面中的其他控件加以区别
```



##### 文本域和菜单/列表

- 文本域

```
<textarea name="文本域名称" value="文本域默认值" rows="行数" cols="列数"></textarea>

#name：文本域的名称
#rows：文本域的行数
#cols：文本域的列数
#value：文本域的默认值
```

- 菜单/列表

【主要用来给定答案中的一种，这类选择答案比较多】

```
<select name="" size="" multiple="multiple" >
           <option value="" selected="selected">选项显示内容</option>
           <option value="选项值" >选项内容</option>
...
    </select>
```

```
name，列表/菜单名称，用于和页面中的其他控件加以区别

size，定义列表/菜单文本框在页面中显示的长度

multiple，表示列表/菜单内容可多选

value，用于定义列表/菜单的选项值

selected，默认被选中
```



***





#### 表格table

##### 基本表格

- 基本表格的制作

```
#用于制作表格的主要标签
<table>   表格标签
<tr>      行标签
<td>      单元格标签
```

```
#语法：
<table>
<tr>
<td>单元格内的文字</td>
<td>单元格内的文字</td>
...
</tr>
<tr>
<td>单元格内的文字</td>
<td>单元格内的文字</td>
...
</tr>
...
</table>
```

- 表头的设置【表头一般位于表格第一行，用来表明该列的内容类别，用<th>和</th>标签来表示】

```
#<table>表格标签，<caption>表头标签，<th>表头单元格标签，<tr>行标签，<td>普通单元格标签
#语法：
<table>
    <caption>表格标题</caption>
    <tr>
          <th>表格的表头</th>
          <th>表格的表头</th>
          ...
    </tr>
    <tr>
           <td>单元格内的文字</td>
           <td>单元格内的文字</td>
           ...
    </tr>
     ...
</table>
```

##### 表格的高级应用

- 表格的样式

```
<table>
<caption>表格标题</caption>
<tr>
<th>表格的表头</th>
<th>表格的表头</th>
...
</tr>
<tr>
<td><img src="引入图片的路径"></td>
<td><img src="引入图片的路径"></td>
...
</tr>
...
</table>
```

- 表格的合并

```
#语法：
<td colspan="跨的列数">
<td rowspan="跨的行数">     #使用<tr>行标签中的rowspan属性，将多行合并成一行
```

- 表格的分组

可以使用<colgroup>标签进行样式标签控制，like，设置单元格的背景颜色、字体大小等。

```
#语法：
<table>
<colgroup>
   <col style="background-color:颜色值">
<col style="background-color:颜色值">
<tr>
<td>单元格内的文字</td>
<td>单元格内的文字</td>
...
</tr>
...
</table>
```

***





#### 框架iframe

【iframe元素会创建包含另外一个文档的内联框架（即行内框架）】

```
属性                          值
align                    left、right、top、middle、bottom
frame border             1、0
height                   pixels、%
width                    pixels、%
longdesc                 URL
marginheight             pixels
marginwidth              pixels
name                     frame_name
sandbox                  ""、allow-forms、allow-same-origin、allow-scripts、allow-top-navigation
scrolling                yes、no、auto
seamless                 seamless
src                      URL
srcdoc                   HTML_code
```

###### 传值(postMessage)

postMessage方法允许来自不同源的脚本采用异步方式进行有限的通信，可以实现跨文本档、多窗口、跨域消息传递。

**语法： otherWindow.postMessage(message, targetOrigin, [transfer]);** 

```
otherWindow：其他窗口的引用，如iframe的contentWindow、执行window.open返回的窗口对象、或者是命名过或数值索引的window.frames。
message：将要发送到其他window的数据。
targetOrigin：指定那些窗口能接收到消息事件，其值可以是字符串“*”表示无限制，或者是一个URL。
transfer：是一串和message同时传递的Transferable对象，这些对象的所有权将被转移给消息的接收方，而发送方将不再保留所有权。

```

postMessage方法被调用时，会在所有页面脚本执行完毕之后像目标窗口派发一个MessageEvent消息，该MessageEvent消息有四个属性：

```
type：表示该message的类型
data：为postMessage的第一个参数
origin：表示调用postMessage方法窗口的源
source：记录调用postMessage方法的窗口对象


```

***





#### HTML5特性

- 语义标签

```
标签
<header>   定义文档的头部区域
<footer>   定义文档的尾部区域
<nav>      定义文档的导航
<section>  定义文档中的节
<article>  定义文章
<aside>    定义页面以外的内容
<details>  定义用户可看的/隐藏的额外细节
<summary>  标签包含details元素的标题
<dialog>   定义对话框
<figure>   定义自包含内容，如图库
<main>     定义文档主内容
<mark>     定义文档的主内容
<time>     定义日期/时间
```



- 增强型表单

```
#新增的五个表单元素
<datalist>  用户会在他们输入数据时看到域定义选项的下拉列表
<progtess>  进度条
<meter>     刻度值，计量温度，重量等
<keygen>    通过一种验证用户的可靠方法，生成公钥和私钥
<output>    用于不同类型的输出，比如：尖酸/脚本输出
```

```
#新增的表单属性
placeholder   输入框默认提示文字
required      要求输入的内容可为空
pattern       描述一个正则表达式验证输入的值
min/max       设置元素最小/最大值
step          为输入域规定的合法的数字间隔
height/width  用于image类型<input>标签图像高度/宽度
autofocus     规定在页面加载时，域自动获得焦点
multiple      规定<input>元素中可选择多个值
```

- 视频和音频

```
#音频
<audio controls>
   <source src="horse.ogg" type="audio/ogg">
   <source src="horse.mp3" type="audio/mpeg">
</audio>
```

```
#视频
<video width="320" height="240" controls>
     <source src="movie.mp4" type="video/mp4">
     <source src="movie.ogg" type="video/ogg">
</video>
```

- Canvas绘图

- SVG绘图

- 地理定位

- 拖放API
- WebWotker
- WebStorage
- WebSocket









