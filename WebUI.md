## 学习目标

1. 掌握主要的HTML标记（html5）
2. 掌握Css的基本语法——选择器（Css3）
3. 掌握Css的常用样式（Css3）
4. 掌握JavaScript基本语法、DOM模型、内置对象
5. 掌握JavaScript自定义对象几种方式**
6. 掌握jQuery的选择器
7. 掌握jQuery的Ajax操作
8. 掌握Boostrap框架的常用组件
9. 结果——使用Bootstrap（也可以选择其他）框架搭建前端页面，使用Ajax请求后台数据
10. 开发工具——WebStorm、HBuilder
11. 测试浏览器——Chrome、Firefox

## 0831——Html基本标记

### 1. Html简介

​	超文本标记语言（HyperText Markup Language，简称：HTML）是一种用于创建网页的标准标记语言。

​	也是一种编程语言，被浏览器**解释**来呈现最终的效果！

### 2. 基本语法

​	1）页面的源文件 *.html , *.htm

​	2）不区分大小写、不识别源代码的空格与换行

​	3）页面主要构成

​		<标记  属性="值" ..> 文本 </标记>

​		<标记  属性="值" .. /> 

​	4）注释 

​		<!--  注释内容  -->

​	5）页面基本结构

~~~html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8" />
    <title>Title</title>
</head>
<body>

</body>
</html>
~~~

​	6）标准：html5

### 3. 文档常用标记

​	1）html、head、body  页面三大标记

​	2）标题字标记 h1 -- h6【大小不同，加粗】

​	3）段落 p

​	4）文本格式化

​		b、strong

​		i、em

​		del

​		sub、sup

​		address -- 斜体

​		blockquote -- 引用

​		pre-- 预加载效果，所写即所见

​	5）换行——\<br/>

​		水平线——\<hr/>

### 4. 颜色设置

​	1）HTML 颜色由一个十六进制符号来定义，这个符号由红色、绿色和蓝色的值组成（RGB）。

每种颜色的最小值是0（十六进制：#00）。最大值是255（十六进制：#FF）。

​	<https://www.runoob.com/html/html-colors.html>

​	2）也可以使用颜色英文单词

### 5. 路径

​	资源定位的描述字符串：

​		从根出发查找所描述的字符串——绝对路径；从当前文件出发查找所描述的字符串——相对路径。

​	1）相对路径与绝对路径

​		绝对路径 :

​			D:\OO\Desktop\Session\3+1\WebUI\Demo\test1.html  【Win】

​			/opt/home/oo/Demo/test2.html	【Linux、Max】

​			http://localhost:63342/Demo/test2.html

​		相对路径 :【不以驱动器或者/又或者\ 开头】

​			Demo\test1.html 

​	2）站内资源访问，**一概使用相对路径**

​	3）相对路径描述方式

​			进入某个目录 —— **目录名**

​			返回上一级目录 —— **../**

​			Demo/

​				index.html

​				pages/

​					admin/

​						userManager.html

​					login.html

​				assets/

​					imgs/

​						default.png

​			index.html 引用 login.html ==》pages/login.html

​			login.html  引用index.html ==》../index.html

​			index.html 引用 default.png ==》assets/imgs/default.png

​			login.html 引用 default.png ==》../assets/imgs/default.png

​			userManager.html引用 default.png ==》../../assets/imgs/default.png

## 0901——超链接、多媒体、列表、表格、框架

### 1. 超链接 a

​	1）链接设置

~~~html
<a href="链接到谁url" target="目标资源打开位置">链接表现内容--文本或者图片等</a>
~~~

​	【说明】

​			target 属性值 

​				\_self(默认值)、\_blank、_top、\_parent、frameName

​	2）锚点链接

​		定位某个页面的指定位置。

​		需要两步完成：

​			-- 制作锚点\<a name="锚点名">\</a>，要链接到的位置

​			-- 创建链接 \<a href="url#锚点名">xxx\</a>，如果链接到当前页面锚点，href属性可以没有url部分

### 2. 多媒体资源

​	1）图片-img

~~~html
<img src="url" width="" height="" alt="图片不能加载时显示的文本"/>
~~~

​	2）音频-audio      *.mp3 、*.ogg、.wav

​		显示控制台——chrome与Firefox没有控制台，不自动播放

~~~html
<audio src="url" controls="controls">
	音频不能播放时所显示的文本
</audio>
~~~

~~~html
<audio controls="controls">
	<source src="a.ogg"/>
	<source src="a.mp3"/>
	...
	音频不能播放时所显示的文本
</audio>
~~~

​	3）视频-video  *.mp4 、*.ogg、.webM

```html
<video src="url" controls="controls">
	视频不能播放时所显示的文本
</video>
```

```html
<video controls="controls">
	<source src="a.ogg"/>
	<source src="a.mp4"/>
	...
	视频不能播放时所显示的文本
</video>
```

​	4）Flash播放：需要浏览器安装flash播放器插件

~~~html
<embed src="url" width="" height=""></embed>
~~~

### 3. 符号实体

​	实体名称对**大小写敏感**。都是以 & 开头，以 ; 结尾

~~~html
  	空格 —— &nbsp; <br/>
    大于号 —— &gt;<br/>
    小于号 —— &lt;<br/>
    圈C —— &copy; <br/>
    & —— &amp; <br/>
    已注册 —— &reg; <br/>
    TM —— &trade;
~~~

### 4. 列表——制作导航、菜单

​	1）无序列表 ul+li

~~~html
<ul type="disc|square|circle">  <!-- type 设置列表前符号，默认实心圆 -->
	<li>列表内容</li>
</ul>
~~~

​	2）有序列表 ol+li

~~~html
<ol type="i" reversed>   <!-- reversed 序 -->
    <li>Java</li>
    <li>Python</li>
    <li>php</li>
</ol>
~~~

​	3）定义列表 dl+dt+dd

~~~html
	<dl>
        <dt>SSM</dt>
        <dd>Spring</dd>
        <dd>Spring Web MVC</dd>
        <dd>MyBatis</dd>
    </dl>	
~~~

### 5. 框架集【废弃】

​	1）窗口分割，一个窗体加载多个页面

​	2）使用frameset与frame来实现

​		-- 使用frameset进行窗口分割，可以嵌套使用

​			属性 cols|rows="v1 , ... , *" 

​		-- 使用frame加载页面

~~~html
<frameset rows="150 , *">
    <frame src="top.html" />
    <frameset cols="180 , *">
        <frame src="left.html" />
        <frame src="right.html" />
    </frameset>
    <noframes>
        <body>
        <h3>对不起，您的浏览器不支持Frameset框架集</h3>
        </body>
    </noframes>
</frameset>
~~~

### 6. 框架 【后台管理】

​	1）使用iframe实现，能够在窗体的任意位置加载一个独立的页面

~~~html
<iframe src="frame/right.html" width="100%" height="500" name="showFrame" frameborder="1"/>
~~~

​	其中 frameborder="0|1"

​	2）如果超链接页面希望在iframe中显示，可以将超链接的target属性值设置为这个iframe的name属性值。

### 7. 表格

​	1）标记 table 、tr、th|td、caption、thead、tbody、tfoot

​	2）table的主要属性

​			- border="0|1"

​			- cellspacing="0"  单元格边框线与表格外围边框线之间的距离

​			- cellpadding  单元格内容和单元格边框之间的距离

​			- width

​	3）单元格合并

​		td或者th使用 colspan或者rowspan

​		【注】一旦使用 thead、tbody、tfoot，单元格合并时不能跨越区域

​	4）tr、td、th的其他属性

​		width、height、bgColor、valign="top|middle|bottom"、align="left|center|right"

### 8. div与span

​	1）div与span一般都是搭配css一起使用，这两个标签单独使用时没有其他效果

​	2）div是块级标签；span是行内标签

## 0902——表单、Html5其他标记















































