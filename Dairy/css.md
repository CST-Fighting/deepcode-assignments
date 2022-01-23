- # css

  - #### 引入方式：行内/内部/外部

  ##### 内部样式：

  语法：在head标签添加style标签,例如：

  ```
  <style type="text/css">
       div{background-color:red;}
  </style>
  ```

  ##### 外部样式：

  语法：在head标签添加link标签，在属性href中填写新建的css文件路径--外部样式，；例如：

  ```
  <link rel="styleheet" href="shiyan.css">
  ```

  css文件可以机进行样式修饰，例如：

  ```
  .al{
  background-color:black;
  }
  ```

  ##### 内联样式：

  语法：直接在需要修饰的标签中添加属性style，然后进行修饰，例如：

  ```
  <div style="background-color:#000000:">
  样式表
  </div>
  ```

  三大样式表对同一属性进行操作的解析规则
  （1）内联样式权重最大
  说明：若三大样式对同一标签的同一属性进行修饰，则显示的是内部样式的修饰结果
  （2）外部样式和内部样式——就近原则
  说明：谁离结构近显示谁的修饰结果

  

  ***

  

  - #### 选择器（前四个最常用）
    
    css语法：
    
    ```
    选择器{
    属性名：属性值；属性名；属性值
    }
    ```
    
    
    
    - ##### 通用选择器
    
    ​         【”*“，给所有的标签加样式，通配符。选择文档中所有的元素】                                                                                                                                                                                                                                                                                                          
    
    ```
    语法：
    *{属性:属性值;}
    ```
    
    
    
    - ##### 标签选择器
    
      也叫元素选择器，语法：
    
      ```
      标签名{属性1：属性值1；属性2：属性值2；属性3：属性值3；...}
      ```
    
      ```
      html{color:black;}
      h1{color:red;}
      a{color:yellow}
      ```
    
      
    
       实例：
    
      ```
      <!DOCTYPE html>
      <html lang="en">
      <head>
       <meta charset="UTF-8">
       <title>Document</title>
       <style type="text/css">
        p {
         color:green;
         font: italic 700 32px "微软雅黑";
        }
       </style>
      </head>
      <body>
       <p>标签选择器例子</p >
      </body>
      </html>
      ```
    
      ​                                                                                                                                        
    
    - ##### id 选择器
    
    类似于类选择器，但也有区别：ID选择器前面有一个”#“号，规则：
    
    ```
    #intro{color:red}
    ```
    
    ID选择器不引用class属性的值，而要引用id属性的值
    
    ```
    <p id="little">
    我是谁？你猜！
    </p>
    ```
    
    
    
    - ##### class 选择器
    
    也叫类名选择器，于id选择器不同的是：可以在一个页面设置多个相同的classs，好比身份证号没有相同的，却可以同名同姓。
    
    ```
    #语法：
    .class名{属性1：属性值1；属性2：属性值2；....}
    ```
    
    举例：
    
    ```
     <div class="myClass">雄心志四海，万里望风尘</div>
     <div class="myClass">雄心志四海，万里望风尘</div>
     <p class="myClass">雄心志四海，万里望风尘</p >
     <div>雄心志四海，万里望风尘</div>
    ```
    
    **注意事项**
    1：什么时候使用 class 选择器
    
    如果你要为两个或多个元素定义相同的样式，元素可以是相同的，也可以是不同的，建议使用 class 选择器，这样可以减少代码的冗余度。
    
    2：class 名的命名规范
    
    先字母，后数字的命名是允许的，如 a1
    先数字，后字母的命名是不允许的，如 1a
    在 HTML 中定义 class = “1a” ，这是不会报错的，但当你在 CSS 中去引用这个类名时，就会出错，提示你 unexpected token ，翻译过来就是 “意外的标记”。还有，不建议使用下划线“ _” 来命名 CSS 选择器，以便区分 JavaScript 中的变量命名。
    不要以纯数字、中文命名，尽量使用英文字母来表示。
    
    
    
    - ##### 属性选择器
    
    可以给元素增加附加信息。例如：height属性，可以指定div元素的宽度；通过id属性，可将不同的div元素进行区分，且通过JavaScript来控制这个div元素的内容和状态。实例：
    
    ```
    <div id="mr1">编程图书</div>
    <div id="mr1-1">python编程</div>
    <div id="mr1-2">PHP编程</div>
    <div id="mr1-3">Java编程</div>
    <div id="mr1">当代文学图书</div>
    <div id="mr2-1">盗墓笔记</div>
    ```
    
    接下来设置div元素的背景色为黑色：
    
    ```
    <style type="text/css">
    #mr1{background:black}
    </style>
    ```
    
    指定id属性值为”mr1"的这个元素的class属性：
    
    ```
    <div id="mr1" class="divBlack">编程图书</div>
    ```
    
    在使用属性选择器时，需要声明属性和属性值，方法：
    
    ```
    [att=val]   #其中att是属性，val是属性值
    ```
    
    ```
    <style type="text/css">
    [id=mr1]{
    background-color
    }
    </style>
    ```
    
    
    
    - ##### 派生选择器
      
      - ###### 后代选择器
      
      又叫包含选择器，可作为某元素后代的元素。
      
      ```
      h1 em{color:red;}    #将h1元素后代em元素里的文本变成红色，而不改变em元素里文本的元素
      ```
      
      【有些文档不会选中该定义的规则】
      
      ```
      <h1><em>我变红色</em></h1>
      <p><em>我不变红色</em></p>
      ```
      
      在后代选择器中，规则左边的选择器一段包括两个/多个空格分隔的选择器。选择器之间的空格是一种结合符。每个空格可解释为“.....在...中找到”“....作为....的一部分”“....作为...的后代：，但必须要求从右向左读选择器。
      
      - ###### 子元素选择器
      
      也叫子代选择器，只能选择作为某元素子元素的元素。子代选择器用大于号作为结合符，范围小。
      
      ```
      h1>strong{color:red;}   #只选择h1元素的子元素strong
      ```
      
      这个规则会把第一个h1下面的strong变成红色，而第二个h1中的strong不受影响
      
      ```
      <h1><strong>我变红色</strong></h1>
      <h1><strong>我不变红色</strong></h>
      ```
      
      
      
      - ###### 相邻兄弟选择器
      
      可选择紧接在另一个元素后的元素，且二者有相同的父元素。相邻兄弟元素选择器使用”+“作为结合符。
      
      ```
      h1+p{color:yellow;}     #将紧接在h1元素后出现的段落变为黄色
      ```
      
      
      
    - ##### 组合选择器
    
    包含选择器
    
    ```
    格式：包含选择器符名 选择符{样式}
    ```
    
    ```
    例：<html>
    <head>
    <meta charset="utf-8">
    <title>CSS基础</title>
    <style type="text/css">
    #header p { font-size:14px;}
    #main p {font-size:12px;}
    </style>
    </head>
    <body>
    <div id="wrap">
        <div id="header">
            <p>头部区域第1段文本</p >
            <p>头部区域第2段文本</p >
            <p>头部区域第3段文本</p >
        </div>
        <div id="main">
            <p>主体区域第1段文本</p >
            <p>主体区域第2段文本</p >
            <p>主体区域第3段文本</p >
        </div>
    </div>
    </body>
    </html> 
    ```
    
    ###### 子选择器
    
    ```
    格式：父级选择器符名 <选择符>{样式}
    ```
    
    ```
    例：<html>
    <head>
    <meta charset="utf-8">
    <title>CSS基础</title>
    <style type="text/css">
    span { font-size:12px;}
    div > span { font-size:16px;}
    div > .font24px { font-size:20px;}
    #box > .font24px { font-size:24px;}
    </style>
    </head>
    <body>
    <h2><span>HTML文档树状结构</span></h2>
    <div id="box"><span class="font24px">问君能有几多愁，恰似一江春水向东流。</span></div>
    <div><span class="font24px">问君能有几多愁，恰似一江春水向东流。</span></div>
    <div><span>问君能有几多愁，恰似一江春水向东流。</span></div>
    </body>
    </html> 
    ```
    
    ###### 相邻选择器
    
    ```
    格式：兄选择符名+弟选择符名{样式}
    ```
    
    例子：p+h3{样式} 只对p后的h3有效
    
    ```
    例：<html>
    <head>
    <meta charset="utf-8">
    <style type="text/css">
    h2, p, h3 {
        margin: 0; /* 清除默认边距 */
        padding: 0; /* 清除默认间距 */
        height: 30px; /* 初始化设置高度为30像素 */
    }
    p+h3 { background-color: #0099FF; /* 设置背景色 */ }
    </style>
    </head>
    <body>
    <div class="header">
        <h2>情况一：</h2>
        <p>子选择器控制p标签，能控制我吗</p >
        <h3>子选择器控制p标签</h3>
        <h2>情况二：</h2>
        <div>我隔开段落和h3直接</div>
        <p>子选择器控制p标签，能控制我吗</p >
        <h3>相邻选择器</h3>
        <h2>情况三：</h2>
        <h3>相邻选择器</h3>
        <p>子选择器控制p标签，能控制我吗</p >
        <div>
            <h2>情况四：</h2>
            <p>子选择器控制p标签，能控制我吗</p >
            <h3>相邻选择器</h3>
        </div>
    </div>
    </body>
    </html>
    ```
    
    ###### 兄弟选择器
    
    ```
    格式：兄选择符名~弟选择符名{样式}
    ```
    
    例子：p~h3{样式} 对p前、p后或者不紧挨着的h3都有效
    
    ```
     例：<html>
    <head>
    <meta charset="utf-8">
    <style type="text/css">
    h2, p, h3 ,h4{
        margin: 0; /* 清除默认边距 */
        padding: 0; /* 清除默认间距 */
        height: 30px; /* 初始化设置高度为30像素 */
    }
    p ~ h3 { background-color: #0099FF; /* 设置背景色 */ }
    </style>
    </head>
    <body>
    <div class="header">
        <h2>情况一：</h2>
        <p>子选择器控制p标签，能控制我吗</p >
        <h3>子选择器控制p标签</h3>
        <h2>情况二：</h2>
        <p>子选择器控制p标签，能控制我吗</p >
        <div>我隔开段落和h3直接</div>
        <h3>相邻选择器</h3>
        <h2>情况三：</h2>
        <h3>相邻选择器</h3>
        <p>子选择器控制p标签，能控制我吗</p >
    </div>
    </body>
    </html> 
    ```
    
    分组选择器
    
    ```
    格式：选择符1，选择符2，....{样式}    #对选择符1，选择符2...都有效
    ```
    
    
    
    - ##### 伪选择器
    
      ###### 伪类选择器
    
    可以使用类选择器把相同的元素定义成不同的样式，针对p元素，实例：
    
    ```
    p.right{text-align:right}
    p.center{text-align:right}
    ```
    
    在页面对p元素使用class属性，来吧定义好的样式指定给p元素，
    
    ```
    <p class="right">文字</p>
    <p class="center">文字</p>
    ```
    
    伪类选择器:p.right可命名为p.class1，然后在页面使用class="class1"
    
    ###### 伪元素选择器
    
    ```
    选择器:伪元素{属性：值}
    ```
    
    ```
    选择器 类名：伪元素{属性：值}    #与类配合
    ```
    
    ```
    #CSS中提供的4个伪元素选择器：
    :first-letter  对应的css样式对指定对象内的第一个字符起作用
    :first-line    对应的css样式对指定对象内的第一行内容起作用
    :before        与内容相关的属性结合使用，用于指定对象内部的前端插入内容
    :after         与内容相关的属性结合使用，用于在指定对象内部的尾部添加内容
    ```
    
    
    
    - ##### 选择器优先级

  ```
  ！important
  style属性内联样式
  ID选择器
  class类选择器，属性选择器和伪类选择器
  标签选择器
  通用选择器，选择符和逻辑组合伪类
  ```

  

  ***

  

  - #### 文档流

  本质为normal flow（普通流、常规流）将窗体自上而下分成一行一行，块级元素从上至下、行内元素在每行中从左至右的顺序依次排放元素。

  注意：本质不存在文档流概念，当一个错误的概念被绝大数人认为是对的，那么它就是对的

  ###### BFC（Block formatting context 块格式化上下文）

    块级格式化上下文：一个独立的渲染区域，只有Block-level box（块级盒）参与，它规定了内部的Block-level Box（块级盒）如何布局，并且与这个区域外部毫不相干

  - 一切皆为框
      div、h1 或 p 元素常常被称为块级元素。这意味着这些元素显示为一块内容，即“块框”。
      与之相反，span 和 strong 等元素称为“行内元素”，这是因为它们的内容显示在行中，即“行内框”。
      可以使用 display属性改变生成的框的类型，可以应用于所有标签。
      即，通过将 display 属性设置为 block，可以让行内元素（比如 <a> 元素）表现得像块级元素一样。
      还可以通过把 display 设置为 none，让生成的元素根本没有框。这样的话，该框及其所有内容就不再显示，不占用文档中的空间。

  - 无名块框
      但是在一种情况下，即使没有进行显式定义，也会创建块级元素。
      类似于把一些文本添加到一个块级元素（例div）的开头，会创建块级元素。如下，即使没有把这些文本定义为段落，它也会被当作段落对待：

  ```
  <div>
      <!--无名块框 some text  -->
      some text
      <p>Some more text.</p >
  </div>
  ```

  在这种情况下，这个框称为无名块框，因为它不与专门定义的元素相关联。

    块级元素的文本行也会发生类似的情况。假设有一个包含三行文本的段落。每行文本形成一个无名框。无法直接对无名块或行框应用样式，因为没有可以应用样式的地方（注意，行框和行内框是两个概念）。但是，这有助于理解在屏幕上看到的所有东西都形成某种框。

  - BFC规则

  ① 内部的Box会在垂直方向，一个接一个地放置；
  ② Box自身垂直方向的位置由margin-top决定，属于同一个BFC的两个相邻Box的margin会发生重叠；
  ③ Box自身水平方向的位置由margin左或右决定(具体依据参照BFC方位)，属于同一个BFC的两个相邻Box的margin会发生叠加。

  ```
  <!DOCTYPE html>
  <html>
  <head>
   <meta charset="UTF-8">
   <title>文档流</title>
   <style type="text/css">
    .box {
     width: 200px;
     height: 200px;
     background-color: orange;
   
     /*默认BFC水平布局方向:从左至右*/
     /*margin-left: 50px;*/
   
     /*更改BFC水平布局方向:从右至左*/
              /*更改块为右浮动，即从右往左计算距离，
               若向右移动则 margin-right: -50px;*/
     float: right;
     margin-right: -50px;
    }
    .b1 {
     width: 200px;
     height: 200px;
     background: red;
     margin-left: 10px;
    }
    .bb1, .bb2 {
     width: 50px;
     height: 50px;
     background: cyan;
     float: left;
    }
    .bb1 {
     margin-left: 20px;
     margin-right: 20px;
    }
    .bb2 {
     margin-left: 20px;
    }
   </style>
  </head>
  <body>
   <!-- b1与b2与box 同在一个区域 | bb1与bb2 同在一个区域 -->
   <div class="b1">
    <div class="bb1"></div>
    <div class="bb2"></div>
   </div>
   <div class="b2"></div>
   
      /*box用来实现BFC的水平布局方式*/
   <div class="box"></div>
  </body>
  </html>
  ```

  

  

  将窗口自上而下分为一行行，并在每行中从左至右顺序排列元素。

  有三种情况使得元素脱离文档流仍存在：

  1）浮动：不占任何正常文档流空间。
  浮动元素的定位还是基于正常的文档流，但是从正常的文档流种抽出，并尽可能地移动至左侧或右侧。
  文字内容会围绕在浮动元素周围。
  当一个元素脱离正常文档流后，仍在文档流中的其他元素会忽略该元素并填补它原先的空间

  2）绝对定位

  3）固定定位

  

  - #### 内联元素 / 块状元素

  行内元素和块元素
  块元素可以设置宽高、默认占据一行，行内元素不能设置宽高、宽度由其内容决定。块元素默认没有高度，有内容才会有高度。行内元素默认没高度和宽度，有内容才会有。行内元素虽然不能设置宽高，但是设置成绝对定位后，可以设置宽高。
  可以将块级元素变成行内元素display:inline;
  一行只有一个块元素，但是行内元素可以有多个。
  空的块元素将在布局中消失。

  

  

  - #### 盒子模型

  ##### 盒子的组合：

  一个盒子由外到内可以分成四个部分：margin（外边距）、border（边框）、padding（内边距）、content（内容）。会发现margin、border、padding是CSS属性，因此可以通过这三个属性来控制盒子的这三个部分。而content则是HTML元素的内容

  盒子的大小：

  指的是盒子的宽度和高度。大多数初学者容易将宽度和高度误解为width和height属性，然而默认情况下width和height属性只是设置content（内容）部分的宽和高。盒子真正的宽和高按下面公式计算：

  ```
  盒子的宽度 = width + padding-left + padding-right + border-left + border-right + margin-left + margin-right
  
  盒子的高度 = height + padding-top + padding-bottom + border-top + border-bottom + margin-top + margin-bottom
  ```

  一般情况下，width和height属性设置的就是盒子的宽度和高度。盒子的宽度和高度的计算方式由box-sizing属性控制。

  ```
  box-sizing属性值
  
  content-box：默认值，width和height属性分别应用到元素的内容框。在宽度和高度之外绘制元素的内边距、边框、外边距。
  
  border-box：为元素设定的width和height属性决定了元素的边框盒。就是说，为元素指定的任何内边距和边框都将在已设定的宽度和高度内进行绘制。通过从已设定的宽度和高度分别减去 边框 和 内边距 才能得到内容的宽度和高度。
  
  inherit：规定应从父元素继承box-sizing属性的值。
  ```

  当box-sizing：content-box时，这种盒子模型成为标准盒子模型，当box-sizing: border-box时，这种盒子模型称为IE盒子模型。

  

  ##### 盒子成分分析

  ###### margin

  ```
  margin，盒子的外边框，他是完全透明的，开发者只可以设置它的边距。
  
  margin包含了上下左右四条边，开发者可以单独设置每一条边的边距。
  
  margin-top：上边距
  margin-buttom：下边距
  margin-left：左边距
  margin-right：右边距
  开发者也可以直接使用简写属性margin同时设置四条边的宽度。
  ```

  ```

  #margin属性后只跟1个值时，同时设置四条边边距相等
  #margin属性后只跟2个值时，第一个为设置上下边距，第二个为设置左右边距
  #margin属性后只跟3个值时，第一个为设置上边距，第二个为设置左右边距，第三个设置下边距
  #margin属性后只跟4个值时，第一个为设置上边距，第二个为设置右边距，第三个为设置下边距，第四个为设置左边距
  ```

  例子：

  ```
  /*margin属性后跟四个值，第一个值设置上边距，第二个是设置右边距，第三个值设置下边距，第四个值设置左边距*/
  margin: 10px 20px 30px 40px;
  /*下面样式与上面的样式等价*/
  margin-top: 10px;
  margin-right: 20px;
  margin-bottom: 30px;
  margin-left: 20px;
  ```

  

  ###### padding

  padding表示盒子的内边距（填充）。与外边距不同，padding不是只能完全透明的，可以设置背景颜色和图片。

  与margin类似，padding包含了上下左右四条边，可以单独设置每一条边的边距。

  ```
  padding-top：上部填充
  padding-bottom：下部填充
  padding-left：左部填充
  padding-right：右部填充
  ```

  也可以直接使用简写属性padding同时设置四条边的宽度。这一部分的用法与margin类似。

  

  ###### border

  border表示盒子的边界，它可以设置成可见的，样式多样的。也可以设置边界的宽度、样式和颜色。

  最基本的，border像margin和padding一样可以分别对每一条边进行设置，也可以使用简写属性border进行设置。

  ```
  border-top：上边界
  border-bottom：下边界
  border-left：左边界
  border-right：右边界
  #当border属性的色值不明确指定时，如border: 1px solid，边框颜色与当前元素的字体颜色color相同。
  border-width：边界宽度
  border-style：边界样式
  border-color：边界颜色
  ```

  border实例1：

  ```
  /*使用简写属性，同时设置四条边界，四条边界的宽度、样式和颜色都是一样的*/
  border: 2px solid green;
  /*下面的样式与上面的样式等价*/
  border-top: 2px solid green;
  border-bottom: 2px solid green;
  border-left: 2px solid green;
  border-right: 2px solid green;
  ```

  ```
  border-sytle属性可取值：
  
  none：定义无边框。
  hidden：与 “none” 相同。不过应用于表时除外，对于表，hidden 用于解决边框冲突。
  dotted：定义点状边框。在大多数浏览器中呈现为实线。
  dashed：定义虚线。在大多数浏览器中呈现为实线。
  solid：定义实线。
  double：定义双线。双线的宽度等于 border-width 的值。
  groove：定义 3D 凹槽边框。其效果取决于 border-color 的值。
  ridge：定义 3D 垄状边框。其效果取决于 border-color 的值。
  inset：定义 3D inset 边框。其效果取决于 border-color 的值。
  outset：定义 3D outset 边框。其效果取决于 border-color 的值。
  inherit：规定应该从父元素继承边框样式。
  ```

  单独设置边界宽度、样式、颜色：

  ```
  border-top-width：上边界宽度
  border-top-style：上边界样式
  border-top-color：上边界颜色
  border-bottom-width：下边界宽度
  border-bottom-style：下边界样式
  border-bottom-color：下边界颜色
  border-left-width：左边界宽度
  border-left-style：左边界样式
  border-left-color：左边界颜色
  border-right-width：右边界宽度
  border-right-style：右边界样式
  border-right-color：右边界颜色
  ```

  

  边界半径 ，也就是圆角。边界半径由属性border-radius进行控制，这是一个简写属性，跟margin、padding等一样，可以有一个、两个、三个或四个值进行设置。同样也可以对盒子的每一个角的半径进行单独设置。

  ```
  border-top-left-radius：左上角
  border-top-right-radius：右上角
  border-bottom-left-radius：左下角
  border-bottom-left-radius：右下角
  #边界半径可以使用 px、em 等长度单位，也可以使用百分数。
  ```

  ```
  border-radius值的个数以及每个值对应控制的位置：
  
  一个值：设置四个角有相同的边界半径；
  两个值：第一个值设置左上角和右下角，第二个值设置右上角和左下角；
  三个值：第一个值设置左上角，第二个值设置右上角和左下角，第三个值设置右下角；
  四个值：第一个值设置左上角，第二个值设置右上角，第三个值设置右下角，第四个之设置左下角。
  ```

  还可以设置x半径和y半径的不同，创建椭圆形角。x半径表示水平半径，y半径表示垂直半径。在border-radius属性中，x半径和y半径用“/”分隔，在border-top-left等四个属性中，传入两个值，第一个值表示x半径，第二个值表示y半径。

  

  ##### 图形边界（border-image）

  ```
  #图形边界中用到的属性：
  border-image：设置图形边界，简写属性
  border-image-source：图形的来源（路径），可以接收一个URL函数或一个渐变作为值。
  border-image-slice：图形的切片大小
  border-image-width：图形边界的宽度
  border-image-repeat：定义图片如何填充边框
  border-image-outset：定义边界内部和内边距之间的额外空间的大小
  ```

  ```
  background-clip属性的值：
  
  border-box：背景延伸到边框外沿（但是在边框之下）。
  padding-box：边框下面没有背景，即背景延伸到内边距外沿。
  content-box：背景裁剪到内容区 (content) 外沿。
  text：背景被裁剪为文字的前景色(只有chrome支持)。
  ```

  

  ##### 盒子阴影（box-shadow）

  语法：

  ```
  none | [inset? && [ <offset-x> <offset-y> <blur-radius>? <spread-radius>? <color>? ] ]#
  ```

  ```
  inset：默认阴影在边框外。使用 inset 后，阴影在边框内（即使是透明边框），背景之上内容之下。
  offset-x, offset-y：这是头两个长度值，用来设置阴影偏移量，相对于border外边线开始计算。offset-x 设置水平偏移量，如果是负值则阴影位于元素左边。offset-y 设置垂直偏移量，如果是负值则阴影位于元素上面。如果两者都是0，那么阴影位于元素后面。这时如果设置了 blur-radius 或 spread-radius 则有模糊效果。
  blur-radius：这是第三个长度值。值越大，模糊面积越大，阴影就越大越淡。 不能为负值。默认为0，此时阴影边缘锐利。
  spread-radius：这是第四个长度值。取正值时，阴影扩大；取负值时，阴影收缩。默认为0，此时阴影与元素同样大。
  color：如果没有指定，则由浏览器决定——通常是color的值，不过目前Safari取透明。
  ```

  设置多个阴影时，使用逗号将每个阴影的值隔开。前面的阴影会在后面阴影之上，如果上层有透明度较低的部分，会与下层的颜色重叠，合成新颜色。

  

  ***

  

  - #### 浮动

    【将元素排除在普通流之外，元素将不在页面中占据空间；将浮动 元素放置在包含框的左边/右边；浮动元素依旧位于包含框之内】
    
    浮动的框可以向左/右，直到他的外边缘碰到包含框或者另一个浮动框的边框为止

  浮动元素的外边缘不会超过其父元素的内边缘；浮动元素不会互相重叠；浮动元素不会上下浮动；任何元素一旦浮动，display属性即将完全失效均可以设置宽高，并且不会独占一行。

  ```
  语法：float:none/left/right
  ```

  

  ***

  

  - #### 定位

  ##### 三种基本的定位机制：普通流、浮动流、定位流。

  普通：上下排列的布局（注：大部分情况）

  浮动：左右排列的布局（注：大部分情况）

  定位：层叠（叠加）排列的布局  （注：大部分情况）

  定位属性：position  ：检索或设置对象的定位方式。

  1、static：默认值；没有定位；   （可以用于取消元素之前的定位设置）

  2、relative：相对定位 （参照物：自己所在的位置）

  特点：  如果没有定位偏移量，对元素本身没有任何影响

  不使元素脱离文档流，空间是会被保留。

  不影响其他元素布局

  left、top、right、bottom是相对于当前元素自身进行偏移的 ，不能独自存在，必须配合定位元素一起使用 。

  3、 absolute : 绝对定位 （参照物：包含块—该元素的祖先级元素）

  使元素完全脱离文档流

  使内联元素支持宽高 （让内联具备块特性）

  使块元素默认宽根据内容决定（让块具备内联的特性）

  如果有定位祖先元素相对于定位祖先元素发生偏移，没有定位祖先元素相对于整个文档发生偏移（绝对、相对、固定）

  注：如果祖先元素中有多个元素具备定位模式，那么是已离自己最近的祖先元素进行偏移。默认情况下是相对可视窗口进行定位的

  

  ##### 包含块的概念：

  ###### 包含块绝对定位的基础：

  绝对定位元素会根据包含块进行绝对定位，默认情况下
  ，浏览器的可视窗口是一个大的包含块，默认情况下，绝对定位元素会相对浏览器的可视窗口进行定位；如果他的祖先级元素定义了包含块，那他就最近的祖先级元素进行绝对定位。

  怎么给他的祖先级元素定义成包含块：  给祖先级元素添加position：relative/absolute/fixed。

  ###### 绝对定位和相对定位的区别：

  1、相对定位的参照物是自己本身所在的位置，绝对定位的参照物的是包含块

  2、相对定位是不会脱离文档流的，而且不会对页面的布局产生影响；绝对定位是会脱离文档流的，原来的位置就不在占有的，后面的内容会把位置补上去。

  ```
  z-index
  auto |number
  ```

  检索或设置对象的层叠顺序。

  auto：默认值。

  number:无单位的整数值。可为负数

  没有设置z-index时，最后写的对象优先显示在上层，设置后，数值越大，层越靠上；

  注：他只针对于具有定位属性的元素起作用；

  4、固定定位： fixed  （参照物：始终都是 相对于整个浏览器窗口进行固定定位的）

  使元素完全脱离文档流

  使内联元素支持宽高 （让内联具备内联块特性）

  使块元素默认宽根据内容决定（让块具备内联块的特性）

  相对于整个浏览器窗口进行偏移，不受浏览器滚动条的影响不会受到祖先元素的影响。

  5、 黏性定位: sticky

  在没有到达指定位置的时候，是没有定位效果的，到达了指定位置，就变成了固定模式。

  

  - #### 层叠规则

     1）找出所有相关的规则，这些规则都包含一个选择器

  2）计算声明的优先级：

  先按来源排序

  再按选择器的特殊性排序

  最终按顺序

  

  

  - ### CSS3

  ##### 圆角边框border-radius

  ##### 盒子阴影box-shadow

  ##### 文字阴影text -shadow

  ##### css3新增选择器

  ######       属性选择器

  ######       结构伪类选择器（:first-child  、 :last-child  、  :nth-child）

  ######       伪元素选择器

  ##### css3盒子模型

  ##### 图片变模糊

  ##### css3过渡transition

  ######       进度条案例

  ##### css3 2D转换transform

  ######       移动：translate

  ######       水平和垂直居中方法

  ######       旋转：rotate

  ######       缩放：scale

  ######       2D转换综合写法及顺序

  

  ##### CSS3 动画animation

  ######      动画的基本使用

  ######      动画的常见属性

  ######      速度曲线细节

  ######       动画简写属性

  ##### css3 3D转换

  ######     3D位移

  ######     3D旋转：rotate3d(x,y,z)

  ######      透视：perspective

  ##### 3D呈现transform-style

####  