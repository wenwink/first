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

## 0902——表单、Html5其他标记、head中的子标记

### 1. 表单

​	**【要求】掌握标记和理解属性**

​	1）收集用户信息，和用户的交互，比如登录、注册、搜索、按钮

​	2）表单标记

~~~html
<form method="get|post" action="url" target="" enctype="">
    <!-- 表单元素 -->
</form>
~~~

~~~
method  --  表单的提交方式
			get ： url?表单元素名=值&表单元素名=值&...       表单元素值和url一起提交到服务器端
			post： 表单元素值单独发送到服务器端			   安全性更高
action  --  表单提交位置
			表单中点击“提交”按钮，页面将发生跳转，跳转到 action所指向的url页面
			如果有“提交”按钮，但是action没有设置该属性，则跳转到本页面
enctype --  表单中有文件上传，必须设置该属性，而且属性值为 "multipart/form-data"
~~~

​	3）表单元素标记

**【切记】除“按钮”外，其他表单元素必须设置 “name”属性** -- 服务器端依赖name属性值获取表单元素值

-- input 标记：单行输入文本域、密码域、单选按钮、多选按钮、文件域、按钮

​				h5 - input的type增加了更多的属性值，主要约束数据类型，限制数据格式

​				【**为一组的radio或者checkbox，name属性值必须相同，每个元素必须设置value**】

​				【value属性设置默认值或者选中本项的值】

~~~html
主要属性 ：
	type ： 设置input表单元素的类型，默认是单行输入文本域
			text	默认值 
			password
			hidden	隐藏域，页面不显示该元素，但是该元素的value值可以提交到服务器端
			radio		单选按钮 ，可以使用属性 checked
			checkbox	多选按钮 ，可以使用属性 checked
			file		文件域
			button		普通按钮 -- 结合js一起使用
			submit		提交按钮 -- 表单提交
			reset		重置按钮 -- 表单恢复初始状态
			image		图像提交按钮，必须搭配src属性一起使用
			------------------------
			email
			url
			tel
			number		可以使用属性 min 与  max
			color		提交的属性值是 #rrggbb
			search
			range
			date、time、datetime、datetime-local、month、week【第三方插件日期选择】
			
	  value :
	  		设置值
	  checked ：
	  		单选和复选使用，初始时选中			
~~~

~~~html
其他属性 ：
		placeholder="提示信息"
		readonly	只读状态，可以获取焦点
		disabled	禁用状态【外观灰掉】，不能获取焦点，而且该表单元素的值不会提交到服务器端
		required	要求该项必填
		autocomplete="on|off"	浏览器是否记录客户输入的内容
~~~

-- select标记：下拉菜单、列表

​		结合option标记一起使用，使用option设置菜单或者列表项

​		 optgroup标记 将option分组 , 使用属性 label

~~~html
select 默认实现 下拉菜单
	   如果做列表，搭配属性 multiple ， 可以同时设置页面初始显示项 size
option 标记
		<option value="">文本</option>
		如果不设置value属性，提交的值同页面显示值
		可以设置属性 selected
~~~

-- textarea标记：多行文本域【富文本编辑器--第三方插件】

~~~html
<textarea cols="" rows="">默认值</textarea>
~~~

-- button标记：按钮

~~~html
<button type="submit(默认)|reset|button">文本</button>
~~~

-- datalist 为 input输入框提供值选择列表

~~~html
<input type="text" name="searchFrom" list="searchData">
<datalist id="searchData">
<option value="Baidu">百度</option>
<option value="Sousou">搜搜</option>
<option value="Google">谷歌</option>
</datalist>
~~~

-- 【了解】fieldset + legend  标记 ：为表单提供边框和标题

~~~
<form>
	<fieldset>
		<legend>标题</lengend>
	<表单元素>
	</fieldset>
</form>
~~~

-- label 标签使用for属性关联表单元素，要求被关联的表单元素提供id属性

~~~html
<p>
    <label for="loginName">账号</label>
    <input type="text" name="name" id="loginName" required />
</p>
~~~

### 2. html5新增一些标记

​	1）表示结构的块级标记

​		**header、footer、nav**、hgroup、article、section、aside

​	2）figure 与 figcaption

​		区域划分，并且添加标题

~~~html
    <figure>
        <figcaption>这是一个男性猴子</figcaption>
        <img src="../assets/imgs/male.jpg" /> <!-- 多媒体资源引入 -->
    </figure>
~~~

​	3）details与summery

~~~html
<details>
        <summary>SSM</summary>
        <ul>
            <li>Spring</li>
            <li>Spring Web MVC</li>
            <li>MyBatis</li>
        </ul>
    </details>
~~~

​	4）中文添加拼音

~~~html
<ruby>
	饕<rp>(</rp><rt>tāo</rt><rp>)</rp>
	餮<rp>(</rp><rt>tiè</rt><rp>)</rp>
</ruby>
~~~

​	5）其他部分

~~~html
<dialog open>这是打开的对话窗口</dialog><!--支持性不好-->
<mark>标记：内容会有黄色底背景</mark> <br />
<progress max="100" value="10"></progress><br />
<meter min="0" max="100" value="30"></meter><br />
<time>2017-03-10</time>
<wbr></wbr> <!-- 安全换行 -->
~~~

### 3. head内部的子标记

​	1）title

​	2）style  -- css样式

​	3）script -- 可以出现在head或者body中，设置js代码，或者引入外部js文件

​	4）link -- 引入外部css样式文件

​	5）base标记

​		设置本页面中所有**相对路径**的基础路径--将所有相对路径前面添加 base标记所设置的url部分

~~~html
<base href="http://www.isoft.com/" target="_blank">
...
<body>
	<a href="user/base.html">个人中心</a>    
	<!-- 链接的网址是 http://www.isoft.com/user/base.html -->
~~~

​	6）meta标记 -- 设置元信息

​	META 元素通常用于指定网页的描述，关键词，文件的最后修改时间，作者，和其他元数据。

​	元数据可以使用于浏览器（如何显示内容或重新加载页面），搜索引擎（关键词），或其他Web服务。

~~~html
实例 1 - 定义文档关键词，用于搜索引擎：
<meta name="keywords" content="HTML, CSS, XML, XHTML, JavaScript">

实例 2 - 定义web页面描述：
<meta name="description" content="Free Web tutorials on HTML and CSS">

实例 3 - 定义页面作者：
<meta name="author" content="Hege Refsnes">

实例 4 - 每30秒刷新页面：
<meta http-equiv="refresh" content="30">

实例 5 - 页面编码设置
<meta charset="UTF-8" />
~~~

明日提交作业——超链接练习+表单练习

## 0903——CSS













































