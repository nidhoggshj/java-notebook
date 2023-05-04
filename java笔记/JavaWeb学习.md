# JavaWeb学习

## 具体代码查询

https://heavy_code_industry.gitee.io/code_heavy_industry/pro001-javaweb/lecture/ 

剔除JSP、EL、JSTL等过时技术，新增Thymeleaf、Vue、Axios、自定义SSM框架等企业实际开发流行技术，并通过三个项目串联所有知识点。  

##  HTML

### HTLM简介

```html

<!--
1.概念
HTML : 超文本标记语言
XML : 可扩展的标记语言
HTML是XML的一个子集

2.XML包含三个部分：
1) XML声明 ， 而且声明这一行代码必须在XML文件的第一行
2) DTD 文档类型定义
3) XML正文
 -->
```

![image-20220618170200431](https://cangimg.oss-cn-beijing.aliyuncs.com/img1%5Cimage-20220618170200431.png)

### 第一个网页代码

```html
/<html>
	<head>
		<title>这是我的第一个网页</title>
		<meta charset="UTF-8">
	</head>
	<body>
		<!--
		HELLO WORLD!<br/>你好，HTML！
		<p>这里是一个段落</p>
		<p>这里是第二个段落</p>
		<img src="D:\sgg2021\0927_javaweb\1109\02.代码\imgs\girl.jpg" width="57" height="73" alt="这里是一张图片"/>
		<h1>标题一</h1>
		<h2>标题一</h2>
		<h3>标题一</h3>
		<h4>标题一</h4>
		<h5>标题一</h5>
		<h6>标题一</h6>
		-->
		武林高手排行榜:
		<ol type="i" start="3">   
			<li>扫地僧</li>
			<li>萧远山</li>
			<li>慕容博</li>
			<li>虚竹</li>
			<li>阿紫</li>
		</ol>
		武林大会人员名单：
		<ul type="circle">
			<li>乔峰</li>
			<li>阿朱</li>
			<li>马夫人</li>
			<li>白世镜</li>
		</ul>

		你是<b><i><u>喜欢</u></i></b>是<b>甜</b>月饼还是<i>咸</i><u>月饼</u>？
		<br/>

		水分子的化学式： H<sub>2</sub>O <br/>
		氧气的化学式： O<sup>2</sup><br/>

		5&lt;10
		10&gt;5
		5&le;10
		10&ge;5
		注册商标 &reg;
		版权符号 &copy;

		<span>赵又廷</span>，夺妻之仇。

		<a href="http://www.baidu.com" target="_self">百度一下</a>

	</body>
</html>

```

### HTLM 符号解释

```html
<!--
1)
html语言是解释型语言，不是编译型
浏览器是容错的

2)
html页面中由一对标签组成：<html></html>
<html> 称之为 开始标签
</html>称之为 结束标签
3)
title 表示网页的标题
4)
可以在meta标签中设置编码方式
5)
<br/>表示换行 。br标签是一个单标签。单标签：开始标签和结束标签是同一个，斜杠放在单词后面
6)
<p> 表示段落标签
7)
img 标签图片标签
	src属性表示图片文件的路径
	width和height表示图片的大小
	alt表示图片的提示
8)
路径的问题：
	1. 相对路径
	2. 绝对路径  从本地得到的
9)
h1~h6 : 标题标签
10)
列表标签:
- ol 有序列表
	start 表示从*开始，type 显示的类型：A a I i 1(deafult) 字母 罗马数字
- ul 无序列表
	type disc(default) , circle , square
11) u 下划线 b 粗体  i 斜体

12) 上标 sup   下标 sub

13) HTML中的实体： 小于号 &lt;大于号 &gt; 大于等于号 &ge 小于&le; 版权 &copy;
百度HTML实体 

14) span 不换行的块标记

15) a 表示超链接
		href 链接的地址
		target:
			_self 在本窗口打开
			_blank 在一个新窗口打开
			_parent 在父窗口打开
			_top  在顶层窗口打开
>百度一下为超链接的名字

16) div 层
-->
```

### 表格标签学习

```html
<html>
	<head>
		<title>表格标签的学习</title>
		<meta charset="UTF-8">
		
	</head>
	<body>
		<table border="1" width="600" cellspacing="0" cellpadding="4">
			<tr align="center">
				<th>姓名</th>
				<th>门派</th>
				<th>成名绝技</th>
				<th>内功值</th>
			</tr>
			<tr align="center">
				<td>乔峰</td>
				<td>丐帮</td>
				<td>少林长拳</td>
				<td>5000</td>
			</tr>
			<tr align="center">
				<td>虚竹</td>
				<td>灵鹫宫</td>
				<td>北冥神功</td>
				<td>15000</td>
			</tr>
			<tr align="center">
				<td>扫地僧</td>
				<td>少林寺</td>
				<td>七十二绝技</td>
				<td>未知</td>
			</tr>
		</table>
		<hr/>
		<table border="1" cellspacing="0" cellpadding="4" width="600">
			<tr>
				<th>名称</th>
				<th>单价</th>
				<th>数量</th>
				<th>小计</th>
				<th>操作</th>
			</tr>
			<tr align="center">
				<td>苹果</td>
				<td rowspan="2">5</td> --占据两行
				<td>20</td>
				<td>100</td>
				<td><img src="imgs/del.jpg" width="24" height="24"/></td>
			</tr>
			<tr align="center">
				<td>菠萝</td>
				<td>15</td>
				<td>45</td>
				<td><img src="imgs/del.jpg" width="24" height="24"/></td>
			</tr>
			<tr align="center">
				<td>西瓜</td>
				<td>6</td>
				<td>6</td>
				<td>36</td>
				<td><img src="imgs/del.jpg" width="24" height="24"/></td>
			</tr>
			<tr align="center">
				<td>总计</td>
				<td colspan="4">181</td> --占据4列
			</tr>
		</table>
	</body>
</html>
<!--
17) 表格	table
	行		tr
	列		td
	表头列	th

	table中有如下属性（虽然已经淘汰，但是最好了解一下）
	- border：表格边框的粗细
	- width:表格的宽度
	- cellspacing：单元格间距
	- cellpadding：单元格填充

	tr中有一个属性： align -> center , left , right 

	rowspan : 行合并
	colspan : 列合并

-->
```

![image-20220618172241669](https://cangimg.oss-cn-beijing.aliyuncs.com/img1%5Cimage-20220618172241669.png)





```html
<html>
	<head>
		<title>表单标签的学习</title>
		<meta charset="UTF-8">
		
	</head>
	<body>
		<form action="demo04.html" method="post">
			昵称：<input type="text" name ='nickname' value="请输入你的昵称"/><br/> --name ='nickname' 不能省
			密码：<input type="password" name="pwd"/><br/>
			性别：<input type="radio" name="gender" value="male"/>男
	  			  <input type="radio" name="gender" value="female" checked/>女<br/> --name 一致才有互斥的效果  checked 默认选中女
            checked=‘checked’ 直接省略
			爱好：<input type="checkbox" name="hobby" value="basketball"/>篮球
				  <input type="checkbox" name="hobby" value="football" checked/>足球
				  <input type="checkbox" name="hobby" value="earth" checked/>地球<br/>
			星座：<select name="star">
					<option value="1">白羊座</option>
					<option value="2" selected>金牛座</option> --默认金牛座
					<option value="3">双子座</option>
					<option value="4">天蝎座</option>
					<option value="5">天秤座</option>
				  </select><br/>
			备注：<textarea name="remark" rows="4" cols="50"></textarea><br/>
			<input type="submit" value=" 注 册 "/>
			<input type="reset" value="重置"/> -恢复到默认情况
			<input type="button" value="这是一个普通按钮"/>
		</form>
	</body>
</html>

<!--
18) 表单	form  action="demo04.html"  发的目的地  method="post"发送方式常用方式为保密方式

19) input type="text" 表示文本框 ， 其中 name属性必须要指定，否则这个文本框的数据将来是不会发送给服务器的
	input type="password" 表示密码框
	input type="radio" 表示单选按钮。需要注意的是，name属性值保持一致，这样才会有互斥的效果;可以通过checked属性设置默认选中的项
	input type="checkbox" 表示复选框。name属性值建议保持一致，这样将来我们服务器端获取值的时候获取的是一个数组
	select 表示下拉列表。每一个选项是option，其中value属性是发送给服务器的值 , selected表示默认选中的项
	textarea 表示多行文本框（或者称之为文本域）,它的value值就是开始结束标签之间的内容
	input type="submit" 表示提交按钮
	input type="reset" 表示重置按钮
	input type="button" 表示普通按钮


-->
```

![image-20220618173143085](https://cangimg.oss-cn-beijing.aliyuncs.com/img1%5Cimage-20220618173143085.png)

![image-20220618173208392](https://cangimg.oss-cn-beijing.aliyuncs.com/img1%5Cimage-20220618173208392.png)



### HTML分区域

```html
<html>
	<head></head>
	<frameset rows="20%,*" > <!-- frameborder="no" -->
		<frame src="frames/top.html"/>
		<frameset cols="15%,*">
			<frame src="frames/left.html"/>
			<frameset rows="80%,*">
				<frame src="frames/main.html"/>
				<frame src="frames/bottom.html"/>
			</frameset>
		</frameset>
	</frameset>
</html>

<!--
frameset 表示页面框架 ， 这个标签已经淘汰，了解，不需要掌握
frame表示框架中的具体页面引用

iframe在一个页面嵌入一个子页面

-->
```

![image-20220619075551968](https://cangimg.oss-cn-beijing.aliyuncs.com/img1%5Cimage-20220619075551968.png)



### 总结

```html
<!--
1.HTML是解释型的文本标记语言，不区分大小写
2.html,head,title,meta,body,br,p,hr,div,table,form,u,i,b,sup,sub,&nbsp;,span,ul,ol,li,tr,td,th,h1-h6,a,input,select,textarea,img
2-1. html , head , title , meta , body , br , ul , ol , h1-h6 , a , img , &nbsp;, p , div , span
2-2. table tr , th , td 
2-3. form(action='' , method='post') input type='text,pasword,radio,checkbox,submit,button,reset"   <select> , <textarea>
-->
```

## CSS-JS

### CSS简介

```html
<html>
	<head>
		<meta charset="utf-8">
		<!-- 内部样式表 -->
		<style type="text/css">
			/* 被style标签包围的范围是CSS环境，可以写CSS代码 */

			/* 标签样式表，所有p标签样式 */
			p{
				color:red;
			}

			/* 类样式 eg：<p class="f20"> 效果为了比周围标题都大*/
			.f20{
				font-size:20px;
			}
           /* ID样式  <p id="p4">
            #p4{
                background-color:pink;
                front-size:24px;
                front-weight:bolder;
                front-style:italic;
                front-family:"华文彩云"；
            }
            /*组合样式 <div> </div>之间遵循*/
            /*
            div p{
                color:blue;
            }
            div.f32{-- class=f32 的遵循
                font-size:32px;
                font-family:"黑体"；
            } 
            */
            /*全部添加到一个包中后面调用
            */
            
		</style>
		<!-- 引用外部的CSS样式表文件 -->
		<link rel="stylesheet" href="css/demo01.css">
        /* 当前文件下css文件下的demo01*/
	</head>
	<body>
		<!--
		<p><font color="red">这里是段落一</font></p>
		<p><font color="red">这里是段落二</font></p>
		-->
		<p>这里是段落一</p>
		<p>这里是段落二</p>
		<p class="f20">这里是段落三</p>
		<p id="p4">这里是段落四</p>	<!-- id属性在整个HTML文档中，尽量保持唯一（虽然重复也不会报错） -->

		<div>
			<p><span style="font-size:60px;font-weight:bolder;color:yellow;">HELLO</span></p>
			<span class="f32">World</span>
			<p class="f32">!!!</p>
		</div>

	</body>
</html>

<!--
1. 为什么需要CSS
2. CSS的最基本的分类: 标签样式表、类样式表、ID样式表、组合样式
3. CSS从位置上的分类：嵌入式样式表、内部样式表、外部样式表
-->
```





```html
<html>
	<head>
		<meta charset="utf-8">
		<style type="text/css">
			#div1{
				width:400px;
				height:400px;
				background-color:greenyellow;

				/* 1. border 边框样式 */
				border-width:1px;			/*边框粗细*/
				border-style:solid;		/*边框样式：solid(实线) , dotted(点状线) ... */
				border-color:blue;			/*边框颜色*/

				/* border:4px double blue;*/ 合并写

				/* border-top : 4px dotted blue;*/ 上边框为蓝色虚线
			}

			#div2{
				width:150px;
				height:150px;
				background-color:darkorange;
				
				margin-top:100px;
				margin-left:100px;
				
				/*margin:100px 100px 50px 150px;*/ /* 一个值，四个方向统一；两个值：上下、左右；三个值：上、左右、下；四个值：上右下左 */
			
				/* padding : 填充 */
				padding-top:50px;
				padding-left:50px;
			}

			#div3{--默认在第二个左上角 通过margin-top...使其居中
				width:100px;
				height:100px;
				background-color:aquamarine;
				/*
				margin-top:50px;
				margin-left:50px;
				*/
			}
			#div4{
				width:200px;
				height:200px;
				margin-left:100px;
				background-color:greenyellow;
			}
			body{
				margin:0;
				padding:0;
			}
		</style>
	</head>
	<body>
		<div id="div1">
			<div id="div2">
				<div id="div3">&nbsp;</div>
			</div>
		</div>
		<div id="div4">&nbsp;</div>

	</body>
</html>

<!-- 
IE浏览器：实际尺寸 = width
chrome浏览器：实际尺寸= width+左右borderwidth+padding


CSS盒子模型：
1.border 边框
2.margin 间距
3.padding 填充

-->
```

![image-20220619102522935](https://cangimg.oss-cn-beijing.aliyuncs.com/img1%5Cimage-20220619102522935.png)



```html
<html>
	<head>
		<meta charset="utf-8">
		<style type="text/css">
			body{
				margin:0;
				padding:0;
			}
			#div1{

				width:200px;
				height:50px;
				background-color:greenyellow;

				/* 绝对定位 */
				position:absolute;
				left:100px;
				top:100px;


			}

			#div2{
				width:200px;
				height:50px;
				background-color:pink;

				position:relative;
				float:left;--向左浮动，把后面位置空出来
				margin-left:20px; -- 左边缘位置空20像素
			}

			#div3{
				height:50px;
				background-color:darkorange;
			}

			#div4{
				width:200px;
				height:50px;
				background-color:aqua;

				float:left;
			}
			#div5{
				width:200px;
				height:50px;
				background-color:olivedrab;

				float:left;
			}
			div{
				position:relative; --div全部相对定位
			}
		</style>
	</head>
	<body>
		<!--
		<div id="div1">&nbsp;</div>
		<div id="div2">&nbsp;</div>
		-->
		<div id="div3">
			<div id="div4">&nbsp;</div>
			<div id="div5">&nbsp;</div>
		</div>
	</body>
</html>

<!--
position: absolute -- 绝对定位 , 需要配合使用 left , top
		  relative -- 相对定位 , 一般会和 float , margin , padding .... 一起使用

float 
-->
```

![image-20220619104348165](https://cangimg.oss-cn-beijing.aliyuncs.com/img1%5Cimage-20220619104348165.png)





```html
<html>
	<head>
		<meta charset="utf-8">
		<style type="text/css">
			body{
				margin:0;
				padding:0;
				background-color:#808080;
			}
			div{
				position:relative;
			}
			#div_top{
				background-color: orange;
				height:20%;
			}
			#div_left{
				background-color: greenyellow;
				height:80%;
				width:15%;
				float:left;
			}
			#div_main{
				background-color: whitesmoke;
				height:70%;
				float:left;
				width:85%;
			}
			#div_bottom{
				background-color: sandybrown;
				height:10%;
				width:85%;
				float:left;
			}
			#div_container{
				width:80%;
				height:100%;
				border:0px solid blue;
				margin-left:10%;
				float:left;
			}
		</style>
	</head>
	<body>
		<div id="div_container">
			<div id="div_top">div_top</div>
			<div id="div_left">div_left</div>
			<div id="div_main">div_main</div>
			<div id="div_bottom">div_bottom</div>
		</div>
	</body>
</html>

```

![image-20220619104505042](https://cangimg.oss-cn-beijing.aliyuncs.com/img1%5Cimage-20220619104505042.png)



### 水果HTML界面

```css
*{
	color: threeddarkshadow;
}
body{
	margin:0;
	padding:0;
	background-color:#808080;
}
div{
	position:relative;
	float:left;
}

#div_container{
	width:80%;
	height:100%;
	border:0px solid blue;
	margin-left:10%;
	float:left;
	background-color: honeydew;
	border-radius:8px; --圆角
}
#div_fruit_list{
	width:100%;
	border:0px solid red;
}
#tbl_fruit{
	width:60%;
	line-height:28px;
	margin-top:120px;
	margin-left:20%;
}
#tbl_fruit , #tbl_fruit tr , #tbl_fruit th , #tbl_fruit td{
	border:1px solid gray;
	border-collapse:collapse;--边框合并
	text-align:center;
	font-size:16px;
	font-family:"黑体";
	font-weight:lighter;
	
}
.w20{
	width:20%;
}
.delImg{
	width:24px;
	height:24px;
}
.btn{
	border:1px solid lightgray;
	width:80px;
	height:24px;
}
```



主体代码

```html
<html>
	<head>
		<meta charset="utf-8">
		<link rel="stylesheet" href="css/demo05.css">
	</head>
	<body>
		<div id="div_container">
			<div id="div_fruit_list">
				<table id="tbl_fruit">
					<tr>
						<th class="w20">名称</th>
						<th class="w20">单价</th>
						<th class="w20">数量</th>
						<th class="w20">小计</th>
						<th>操作</th>
					</tr>
					<tr>
						<td>苹果</td>
						<td>5</td>
						<td>20</td>
						<td>100</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr>
						<td>西瓜</td>
						<td>3</td>
						<td>20</td>
						<td>60</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr>
						<td>菠萝</td>
						<td>4</td>
						<td>25</td>
						<td>100</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr>
						<td>榴莲</td>
						<td>3</td>
						<td>30</td>
						<td>90</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr>
						<td>总计</td>
						<td colspan="4">999</td>
					</tr>
				</table>
			</div>
		</div>
	</body>
</html>

```

![image-20220619110311325](https://cangimg.oss-cn-beijing.aliyuncs.com/img1%5Cimage-20220619110311325.png)



### JavaScript

```html
 <html>
	<head>
		<meta charset="utf-8">
		<script language="javascript">
			// String str = "hello world" ;
			
			/*
			var str = "hello world";
			alert(typeof str);
			str = 9999 ;
			alert(typeof str);
			*/
			/*
			var person = new Object();
			person.pid = "p001";
			person.pname="鸠摩智";

			alert(person.pid+"_"+person.pname);
			*/
			//java 方法
			public String hello(String name){
				return "hello to " + name ;
			}

			//js 方法
			function hello(num1 , num2 , name){
				if(num1>num2){
					return "hello to" + name ;
				}else{
					alert("HELLO");
				}
			}


		</script>
	</head>
	<body>
		
	</body>
</html>
<!--
Javascript : 客户端的一个脚本语言
js是一门弱类型的语言 , 变量的数据类型由后面赋的值的类型决定

-->
```



### 鼠标悬浮改变颜色

#### 通过showBGColor和clearBGColor()鼠标悬浮改变颜色

```html
<html>
	<head>
		<meta charset="utf-8">
		<link rel="stylesheet" href="css/demo05.css">
		<script type="text/javascript" src="js/demo07.js"></script>
	</head>
	<body>
		<div id="div_container">
			<div id="div_fruit_list">
				<table id="tbl_fruit">
					<tr>
						<th class="w20">名称</th>
						<th class="w20">单价</th>
						<th class="w20">数量</th>
						<th class="w20">小计</th>
						<th>操作</th>
					</tr>
					<tr onmouseover="showBGColor()" onmouseout="clearBGColor()">
						<td>苹果</td>
						<td onmouseover="showHand()">5</td>
						<td>20</td>
						<td>100</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr onmouseover="showBGColor()" onmouseout="clearBGColor()">
						<td>西瓜</td>
						<td onmouseover="showHand()">3</td>
						<td>20</td>
						<td>60</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr onmouseover="showBGColor()" onmouseout="clearBGColor()">
						<td>菠萝</td>
						<td onmouseover="showHand()">4</td>
						<td>25</td>
						<td>100</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr onmouseover="showBGColor()" onmouseout="clearBGColor()">
						<td>榴莲</td>
						<td onmouseover="showHand()">3</td>
						<td>30</td>
						<td>90</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr>
						<td>总计</td>
						<td colspan="4">999</td>
					</tr>
				</table>
			</div>
		</div>
	</body>
</html>

```

showBGColor()方法

```JavaScript

//当鼠标悬浮时，显示背景颜色
function showBGColor(){
	//event : 当前发生的事件
	//event.srcElement : 事件源
	//alert(event.srcElement);
	//alert(event.srcElement.tagName);	--> TD
	if(event && event.srcElement && event.srcElement.tagName=="TD"){
		var td = event.srcElement ;
		//td.parentElement 表示获取td的父元素 -> TR
		var tr = td.parentElement ;
		//如果想要通过js代码设置某节点的样式，则需要加上 .style
		tr.style.backgroundColor = "navy" ;

		//tr.cells表示获取这个tr中的所有的单元格
		var tds = tr.cells;
		for(var i = 0 ; i<tds.length ; i++){
			tds[i].style.color="white";
		}
	}
}

//当鼠标离开时，恢复原始样式
function clearBGColor(){
	if(event && event.srcElement && event.srcElement.tagName=="TD"){
		var td = event.srcElement ;
		var tr = td.parentElement ;
		tr.style.backgroundColor="transparent";
		var tds = tr.cells;
		for(var i = 0 ; i<tds.length ; i++){
			tds[i].style.color="threeddarkshadow";
		}
	}
}

//当鼠标悬浮在单价单元格时，显示手势
function showHand(){
	if(event && event.srcElement && event.srcElement.tagName=="TD"){
		var td = event.srcElement ;
		//cursor : 光标
		td.style.cursor="hand";
	}

}
```





#### 通过js为主改变鼠标悬浮显示颜色

```html
<html>
	<head>
		<meta charset="utf-8">
		<link rel="stylesheet" href="css/demo05.css">
		<script type="text/javascript" src="js/demo08.js"></script>
	</head>
	<body>
		<div id="div_container">
			<div id="div_fruit_list">
				<table id="tbl_fruit">
					<tr>
						<th class="w20">名称</th>
						<th class="w20">单价</th>
						<th class="w20">数量</th>
						<th class="w20">小计</th>
						<th>操作</th>
					</tr>
					<tr>
						<td>苹果</td>
						<td>5</td>
						<td>20</td>
						<td>100</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr>	
						<td>西瓜</td>
						<td>3</td>
						<td>20</td>
						<td>60</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr>
						<td>菠萝</td>
						<td>4</td>
						<td>25</td>
						<td>100</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr>
						<td>榴莲</td>
						<td>3</td>
						<td>30</td>
						<td>90</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr>
						<td>总计</td>
						<td colspan="4">999</td>
					</tr>
				</table>
			</div>
		</div>
	</body>
</html>


```



.js

```javascript
 window.onload=function(){
	updateZJ();
	//当页面加载完成，我们需要绑定各种事件
	//根据id获取到表格
	var fruitTbl =  document.getElementById("tbl_fruit");
	//获取表格中的所有的行
	var rows = fruitTbl.rows ;
	for(var i = 1 ; i<rows.length-1 ; i++){
		var tr = rows[i];
		//1.绑定鼠标悬浮以及离开时设置背景颜色事件
		tr.onmouseover=showBGColor;
		tr.onmouseout=clearBGColor;
		//获取tr这一行的所有单元格
		var cells = tr.cells;
		var priceTD = cells[1]; //只关注第一列 单价 
		//2.绑定鼠标悬浮在单价单元格变手势的事件
		priceTD.onmouseover = showHand ;
		//3.绑定鼠标点击单价单元格的事件 ----新功能
		priceTD.onclick=editPrice;
	}

}

//当鼠标点击单价单元格时进行价格编辑
function editPrice(){
	if(event && event.srcElement && event.srcElement.tagName=="TD"){
		var priceTD = event.srcElement ;
		//目的是判断当前priceTD有子节点，而且第一个子节点是文本节点 ， TextNode(文本节点)对应的是3  ElementNode(元素节点)对应的是1 防止点击文本框外-非文本节点后，文本节点当前变成空，使得后面input.value = oldPrice 变成空
		if(priceTD.firstChild && priceTD.firstChild.nodeType==3){
			//innerText 表示设置或者获取当前节点的内部文本
			var oldPrice = priceTD.innerText ;
			//innerHTML 表示设置当前节点的内部HTML，点击出现文本框
			priceTD.innerHTML="<input type='text' size='4'/>";
			//<td>5</td>变成了
            //<td><input type='text' size='4'/></td>
			var input = priceTD.firstChild;//获取第一个子节点
			if(input.tagName=="INPUT"){
				input.value = oldPrice ;
				//选中输入框内部的文本
				input.select();
				//4.绑定输入框失去焦点事件 , 失去焦点，更新单价
				input.onblur=updatePrice ;
			}
		}
		
	}
}

function updatePrice(){
	if(event && event.srcElement && event.srcElement.tagName=="INPUT"){
		var input = event.srcElement ;
		var newPrice = input.value ;
		//input节点的父节点是td
		var priceTD = input.parentElement ;
		priceTD.innerText = newPrice ;

		//更新当前行的小计这一个格子的值
		//priceTD.parentElement td的父元素是tr
		updateXJ(priceTD.parentElement);

	}
}

//更新指定行的小计
function updateXJ(tr){
	if(tr && tr.tagName=="TR"){
		var tds = tr.cells;
		var price = tds[1].innerText ;
		var count = tds[2].innerText ;
		//innerText获取到的值的类型是字符串类型，因此需要类型转换，才能进行数学运算
		var xj = parseInt(price) * parseInt(count);
		tds[3].innerText = xj ;

		//更新总计
		updateZJ();
	}

}

//更新总计
function updateZJ(){
	var fruitTbl = document.getElementById("tbl_fruit");
	var rows = fruitTbl.rows ;//获取所有行
	var sum = 0 ;
	for(var i = 1; i<rows.length-1 ; i++){
		var tr = rows[i];
		var xj = parseInt(tr.cells[3].innerText);		//NaN    not a number 不是一个数字
		sum = sum + xj ;
	}
	rows[rows.length-1].cells[1].innerText = sum ;
}




//当鼠标悬浮时，显示背景颜色
function showBGColor(){
	//event : 当前发生的事件
	//event.srcElement : 事件源
	//alert(event.srcElement);
	//alert(event.srcElement.tagName);	--> TD
	if(event && event.srcElement && event.srcElement.tagName=="TD"){
		var td = event.srcElement ;
		//td.parentElement 表示获取td的父元素 -> TR
		var tr = td.parentElement ;
		//如果想要通过js代码设置某节点的样式，则需要加上 .style
		tr.style.backgroundColor = "navy" ;

		//tr.cells表示获取这个tr中的所有的单元格
		var tds = tr.cells;
		for(var i = 0 ; i<tds.length ; i++){
			tds[i].style.color="white";
		}
	}
}

//当鼠标离开时，恢复原始样式
function clearBGColor(){
	if(event && event.srcElement && event.srcElement.tagName=="TD"){
		var td = event.srcElement ;
		var tr = td.parentElement ;
		tr.style.backgroundColor="transparent";
		var tds = tr.cells;
		for(var i = 0 ; i<tds.length ; i++){
			tds[i].style.color="threeddarkshadow";
		}
	}
}

//当鼠标悬浮在单价单元格时，显示手势
function showHand(){
	if(event && event.srcElement && event.srcElement.tagName=="TD"){
		var td = event.srcElement ;
		//cursor : 光标
		td.style.cursor="hand";
	}

}
```



#### 完成删除功能

```HTML
<html>
	<head>
		<meta charset="utf-8">
		<link rel="stylesheet" href="css/demo05.css">
		<script type="text/javascript" src="js/demo09.js"></script>
	</head>
	<body>
		<div id="div_container">
			<div id="div_fruit_list">
				<table id="tbl_fruit">
					<tr>
						<th class="w20">名称</th>
						<th class="w20">单价</th>
						<th class="w20">数量</th>
						<th class="w20">小计</th>
						<th>操作</th>
					</tr>
					<tr>
						<td>苹果</td>
						<td>5</td>
						<td>20</td>
						<td>100</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr>	
						<td>西瓜</td>
						<td>3</td>
						<td>20</td>
						<td>60</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr>
						<td>菠萝</td>
						<td>4</td>
						<td>25</td>
						<td>100</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr>
						<td>榴莲</td>
						<td>3</td>
						<td>30</td>
						<td>90</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr>
						<td>总计</td>
						<td colspan="4">999</td>
					</tr>
				</table>
				<hr/>
				<div id="add_fruit_div">
					<table>
						<tr>
							<td>名称：</td>
							<td><input type='text' id='fname'/></td>
						</tr>
						<tr>
							<td>单价：</td>
							<td><input type='text' id='price'/></td>
						</tr>
						<tr>
							<td>数量：</td>
							<td><input type='text' id='fcount'/></td>
						</tr>
						<tr>
							<th colspan="2">
								<input type='button' class="btn" value="添加"/>
								<input type='button' class="btn" value="重填"/>
							</th>
						</tr>
					</table>
				</div>
			</div>
		</div>
	</body>
</html>

```





```js
window.onload=function(){
	updateZJ();
	//当页面加载完成，我们需要绑定各种事件
	//根据id获取到表格
	var fruitTbl =  document.getElementById("tbl_fruit");
	//获取表格中的所有的行
	var rows = fruitTbl.rows ;
	for(var i = 1 ; i<rows.length-1 ; i++){
		var tr = rows[i];
		//1.绑定鼠标悬浮以及离开时设置背景颜色事件
		tr.onmouseover=showBGColor;
		tr.onmouseout=clearBGColor;
		//获取tr这一行的所有单元格
		var cells = tr.cells;
		var priceTD = cells[1];
		//2.绑定鼠标悬浮在单价单元格变手势的事件
		priceTD.onmouseover = showHand ;
		//3.绑定鼠标点击单价单元格的事件
		priceTD.onclick=editPrice;


		//7.绑定删除小图标的点击事件
		var img = cells[4].firstChild;
		if(img && img.tagName=="IMG"){
			//绑定单击事件
			img.onclick = delFruit ;
		}

	}
}

function delFruit(){
	if(event && event.srcElement && event.srcElement.tagName=="IMG"){
		//alert表示弹出一个对话框，只有确定按钮
		//confirm表示弹出一个对话框，有确定和取消按钮。当点击确定，返回true，否则返回false
		if(window.confirm("是否确认删除当前库存记录")){
			var img = event.srcElement ;
			var tr = img.parentElement.parentElement ;
			var fruitTbl = document.getElementById("tbl_fruit");
			fruitTbl.deleteRow(tr.rowIndex);

			updateZJ();
		}
	}

}

//当鼠标点击单价单元格时进行价格编辑
function editPrice(){
	if(event && event.srcElement && event.srcElement.tagName=="TD"){
		var priceTD = event.srcElement ;
		//目的是判断当前priceTD有子节点，而且第一个子节点是文本节点 ， TextNode对应的是3  ElementNode对应的是1
		if(priceTD.firstChild && priceTD.firstChild.nodeType==3){
			//innerText 表示设置或者获取当前节点的内部文本
			var oldPrice = priceTD.innerText ;
			//innerHTML 表示设置当前节点的内部HTML
			priceTD.innerHTML="<input type='text' size='4'/>";
			// <td><input type='text' size='4'/></td>
			var input = priceTD.firstChild;
			if(input.tagName=="INPUT"){
				input.value = oldPrice ;
				//选中输入框内部的文本
				input.select();
				//4.绑定输入框失去焦点事件 , 失去焦点，更新单价
				input.onblur=updatePrice ;

				//8.在输入框上绑定键盘摁下的事件，此处我需要保证用户输入的是数字
				input.onkeydown=ckInput;
			}
		}
		
	}
}

//检验键盘摁下的值的方法
function ckInput(){
	var kc = event.keyCode ;
	// 0 ~ 9 : 48~57
	//backspace : 8
	//enter : 13
	//console.log(kc);

	if(!( ( kc>=48 && kc<=57 ) || kc==8 || kc==13 )){
		event.returnValue=false;
	}//此时无法输入abcd

	if(kc==13){//输入回车自动失去焦点
		event.srcElement.blur();//blur()失去焦点
	}

}

//更新单价的方法
function updatePrice(){
	if(event && event.srcElement && event.srcElement.tagName=="INPUT"){
		var input = event.srcElement ;
		var newPrice = input.value ;
		//input节点的父节点是td
		var priceTD = input.parentElement ;
		priceTD.innerText = newPrice ;

		//5. 更新当前行的小计这一个格子的值
		//priceTD.parentElement td的父元素是tr
		updateXJ(priceTD.parentElement);

	}
}

//更新指定行的小计
function updateXJ(tr){
	if(tr && tr.tagName=="TR"){
		var tds = tr.cells;
		var price = tds[1].innerText ;
		var count = tds[2].innerText ;
		//innerText获取到的值的类型是字符串类型，因此需要类型转换，才能进行数学运算
		var xj = parseInt(price) * parseInt(count);
		tds[3].innerText = xj ;

		//6. 更新总计
		updateZJ();
	}

}

//更新总计
function updateZJ(){
	var fruitTbl = document.getElementById("tbl_fruit");
	var rows = fruitTbl.rows ;
	var sum = 0 ;
	for(var i = 1; i<rows.length-1 ; i++){
		var tr = rows[i];
		var xj = parseInt(tr.cells[3].innerText);		//NaN    not a number 不是一个数字
		sum = sum + xj ;
	}
	rows[rows.length-1].cells[1].innerText = sum ;
}


//当鼠标悬浮时，显示背景颜色
function showBGColor(){
	//event : 当前发生的事件
	//event.srcElement : 事件源
	//alert(event.srcElement);
	//alert(event.srcElement.tagName);	--> TD
	if(event && event.srcElement && event.srcElement.tagName=="TD"){
		var td = event.srcElement ;
		//td.parentElement 表示获取td的父元素 -> TR
		var tr = td.parentElement ;
		//如果想要通过js代码设置某节点的样式，则需要加上 .style
		tr.style.backgroundColor = "navy" ;

		//tr.cells表示获取这个tr中的所有的单元格
		var tds = tr.cells;
		for(var i = 0 ; i<tds.length ; i++){
			tds[i].style.color="white";
		}
	}
}

//当鼠标离开时，恢复原始样式
function clearBGColor(){
	if(event && event.srcElement && event.srcElement.tagName=="TD"){
		var td = event.srcElement ;
		var tr = td.parentElement ;
		tr.style.backgroundColor="transparent";
		var tds = tr.cells;
		for(var i = 0 ; i<tds.length ; i++){
			tds[i].style.color="threeddarkshadow";
		}
	}
}

//当鼠标悬浮在单价单元格时，显示手势
function showHand(){
	if(event && event.srcElement && event.srcElement.tagName=="TD"){
		var td = event.srcElement ;
		//cursor : 光标
		td.style.cursor="hand";
	}

}
```

#### 作业

demo05

```css
*{
	color: threeddarkshadow;
}
body{
	margin:0;
	padding:0;
	background-color:#808080;
}
div{
	position:relative;
	float:left;
}

#div_container{
	width:80%;
	height:100%;
	border:0px solid blue;
	margin-left:10%;
	float:left;
	background-color: honeydew;
	border-radius:8px;
}
#div_fruit_list{
	width:100%;
	border:0px solid red;
}
#tbl_fruit{
	width:60%;
	line-height:28px;
	margin-top:120px;
	margin-left:20%;
}
#tbl_fruit , #tbl_fruit tr , #tbl_fruit th , #tbl_fruit td{
	border:1px solid gray;
	border-collapse:collapse;
	text-align:center;
	font-size:16px;
	font-family:"黑体";
	font-weight:lighter;
	
}
.w20{
	width:20%;
}
.delImg{
	width:24px;
	height:24px;
}
.btn{
	border:1px solid lightgray;
	width:80px;
	height:24px;
}
#add_fruit_div{
	border:0px solid red;
	width:40%;
	margin-left:30%;
}
#add_fruit_tbl {
	margin-top:32px;
	width:80%;
	margin-left:10%;
	border-collapse:collapse;
}
#add_fruit_tbl , #add_fruit_tbl tr , #add_fruit_tbl td{
	border:1px solid lightgray;
	text-align:center;
	line-height:28px;
}
.w30{
	width:30%;
}

.input{
	padding-left:4px;
	border:1px solid lightgray;
	width:90%;
}
```

demo09

```js
function $(id){
	return document.getElementById(id);
}

window.onload=function(){
	updateZJ();
	//当页面加载完成，我们需要绑定各种事件
	//根据id获取到表格
	var fruitTbl =  $("tbl_fruit");
	//获取表格中的所有的行
	var rows = fruitTbl.rows ;
	for(var i = 1 ; i<rows.length-1 ; i++){
		var tr = rows[i];
		trBindEvent(tr);
	}

	$("addBtn").onclick=addFruit;
}

function trBindEvent(tr){
	//1.绑定鼠标悬浮以及离开时设置背景颜色事件
		tr.onmouseover=showBGColor;
		tr.onmouseout=clearBGColor;
		//获取tr这一行的所有单元格
		var cells = tr.cells;
		var priceTD = cells[1];
		//2.绑定鼠标悬浮在单价单元格变手势的事件
		priceTD.onmouseover = showHand ;
		//3.绑定鼠标点击单价单元格的事件
		priceTD.onclick=editPrice;


		//7.绑定删除小图标的点击事件
		var img = cells[4].firstChild;
		if(img && img.tagName=="IMG"){
			//绑定单击事件
			img.onclick = delFruit ;
		}
}

//添加水果信息
function addFruit(){
	var fname = $("fname").value;
	var price = parseInt($("price").value);//parseInt() 函数解析字符串并返回整数。
	var fcount = parseInt($("fcount").value);
	var xj = price * fcount ;

	var fruitTbl =  $("tbl_fruit");
	var tr = fruitTbl.insertRow(fruitTbl.rows.length-1);
	var fnameTD = tr.insertCell();
	fnameTD.innerText = fname ;

	var priceTD = tr.insertCell();
	priceTD.innerText = price ;

	var fcountTD = tr.insertCell();
	fcountTD.innerText = fcount ;

	var xjTD = tr.insertCell();
	xjTD.innerText = xj ;

	var imgTD = tr.insertCell();
	imgTD.innerHTML = "<img src='imgs/del.jpg' class='delImg'/>";

	updateZJ();

	trBindEvent(tr);

}

function delFruit(){
	if(event && event.srcElement && event.srcElement.tagName=="IMG"){
		//alert表示弹出一个对话框，只有确定按钮
		//confirm表示弹出一个对话框，有确定和取消按钮。当点击确定，返回true，否则返回false
		if(window.confirm("是否确认删除当前库存记录")){
			var img = event.srcElement ;
			var tr = img.parentElement.parentElement ;
			var fruitTbl = $("tbl_fruit");
			fruitTbl.deleteRow(tr.rowIndex);

			updateZJ();
		}
	}

}

//当鼠标点击单价单元格时进行价格编辑
function editPrice(){
	if(event && event.srcElement && event.srcElement.tagName=="TD"){
		var priceTD = event.srcElement ;
		//目的是判断当前priceTD有子节点，而且第一个子节点是文本节点 ， TextNode对应的是3  ElementNode对应的是1
		if(priceTD.firstChild && priceTD.firstChild.nodeType==3){
			//innerText 表示设置或者获取当前节点的内部文本
			var oldPrice = priceTD.innerText ;
			//innerHTML 表示设置当前节点的内部HTML
			priceTD.innerHTML="<input type='text' size='4'/>";
			// <td><input type='text' size='4'/></td>
			var input = priceTD.firstChild;
			if(input.tagName=="INPUT"){
				input.value = oldPrice ;
				//选中输入框内部的文本
				input.select();
				//4.绑定输入框失去焦点事件 , 失去焦点，更新单价
				input.onblur=updatePrice ;

				//8.在输入框上绑定键盘摁下的事件，此处我需要保证用户输入的是数字
				input.onkeydown=ckInput;
			}
		}
		
	}
}

//检验键盘摁下的值的方法
function ckInput(){
	var kc = event.keyCode ;
	// 0 ~ 9 : 48~57
	//backspace : 8
	//enter : 13
	//console.log(kc);

	if(!( ( kc>=48 && kc<=57 ) || kc==8 || kc==13 )){
		event.returnValue=false;
	}

	if(kc==13){
		event.srcElement.blur();
	}

}

//更新单价的方法
function updatePrice(){
	if(event && event.srcElement && event.srcElement.tagName=="INPUT"){
		var input = event.srcElement ;
		var newPrice = input.value ;
		//input节点的父节点是td
		var priceTD = input.parentElement ;
		priceTD.innerText = newPrice ;

		//5. 更新当前行的小计这一个格子的值
		//priceTD.parentElement td的父元素是tr
		updateXJ(priceTD.parentElement);

	}
}

//更新指定行的小计
function updateXJ(tr){
	if(tr && tr.tagName=="TR"){
		var tds = tr.cells;
		var price = tds[1].innerText ;
		var count = tds[2].innerText ;
		//innerText获取到的值的类型是字符串类型，因此需要类型转换，才能进行数学运算
		var xj = parseInt(price) * parseInt(count);
		tds[3].innerText = xj ;

		//6. 更新总计
		updateZJ();
	}

}

//更新总计
function updateZJ(){
	var fruitTbl = $("tbl_fruit");
	var rows = fruitTbl.rows ;
	var sum = 0 ;
	for(var i = 1; i<rows.length-1 ; i++){
		var tr = rows[i];
		var xj = parseInt(tr.cells[3].innerText);		//NaN    not a number 不是一个数字
		sum = sum + xj ;
	}
	rows[rows.length-1].cells[1].innerText = sum ;
}


//当鼠标悬浮时，显示背景颜色
function showBGColor(){
	//event : 当前发生的事件
	//event.srcElement : 事件源
	//alert(event.srcElement);
	//alert(event.srcElement.tagName);	--> TD
	if(event && event.srcElement && event.srcElement.tagName=="TD"){
		var td = event.srcElement ;
		//td.parentElement 表示获取td的父元素 -> TR
		var tr = td.parentElement ;
		//如果想要通过js代码设置某节点的样式，则需要加上 .style
		tr.style.backgroundColor = "navy" ;

		//tr.cells表示获取这个tr中的所有的单元格
		var tds = tr.cells;
		for(var i = 0 ; i<tds.length ; i++){
			tds[i].style.color="white";
		}
	}
}

//当鼠标离开时，恢复原始样式
function clearBGColor(){
	if(event && event.srcElement && event.srcElement.tagName=="TD"){
		var td = event.srcElement ;
		var tr = td.parentElement ;
		tr.style.backgroundColor="transparent";
		var tds = tr.cells;
		for(var i = 0 ; i<tds.length ; i++){
			tds[i].style.color="threeddarkshadow";
		}
	}
}

//当鼠标悬浮在单价单元格时，显示手势
function showHand(){
	if(event && event.srcElement && event.srcElement.tagName=="TD"){
		var td = event.srcElement ;
		//cursor : 光标
		td.style.cursor="hand";
	}

}
```

主代码

```html
<html>
	<head>
		<meta charset="utf-8">
		<link rel="stylesheet" href="css/demo05.css">
		<script type="text/javascript" src="js/demo09.js"></script>
	</head>
	<body>
		<div id="div_container">
			<div id="div_fruit_list">
				<table id="tbl_fruit">
					<tr>
						<th class="w20">名称</th>
						<th class="w20">单价</th>
						<th class="w20">数量</th>
						<th class="w20">小计</th>
						<th>操作</th>
					</tr>
					<tr>
						<td>苹果</td>
						<td>5</td>
						<td>20</td>
						<td>100</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr>	
						<td>西瓜</td>
						<td>3</td>
						<td>20</td>
						<td>60</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr>
						<td>菠萝</td>
						<td>4</td>
						<td>25</td>
						<td>100</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr>
						<td>榴莲</td>
						<td>3</td>
						<td>30</td>
						<td>90</td>
						<td><img src="imgs/del.jpg" class="delImg"/></td>
					</tr>
					<tr>
						<td>总计</td>
						<td colspan="4">999</td>
					</tr>
				</table>
				<hr/>
				<div id="add_fruit_div">
					<table id="add_fruit_tbl">
						<tr>
							<td class="w30">名称：</td>
							<td><input class="input" type='text' id='fname' value="apple"/></td>
						</tr>
						<tr>
							<td>单价：</td>
							<td><input class="input" type='text' id='price' value="5"/></td>
						</tr>
						<tr>
							<td>数量：</td>
							<td><input class="input" type='text' id='fcount' value="100"/></td>
						</tr>
						<tr>
							<th colspan="2">
								<input type='button' id="addBtn" class="btn" value="添加"/>
								<input type='button' class="btn" value="重填"/>
							</th>
						</tr>
					</table>
				</div>
			</div>
		</div>
	</body>
</html>

```



### 小结

![image-20220625100523990](https://cangimg.oss-cn-beijing.aliyuncs.com/img1%5Cimage-20220625100523990.png)





## Web

### web-CS和BS的异同

![01.BS和CS(2)](https://cangimg.oss-cn-beijing.aliyuncs.com/img1%5C01.BS%E5%92%8CCS(2).png)



### Tomcat

![02.server_Tomcat_deploy](https://cangimg.oss-cn-beijing.aliyuncs.com/img1%5C02.server_Tomcat_deploy.png)

tomcat 目录下webappps文件夹建立baidu，再在百度文件夹下建立WEB-INF文件夹

再将相应的程序代码拷贝到baidu文件下，在浏览器输入http://localhost:8080/baidu/demo09.html 即可访问

IDEA可以一键部署，具体操作看视频  shift+F6 改名称





![03.第一次使用Servlet(2)](https://cangimg.oss-cn-beijing.aliyuncs.com/img1%5C03.%E7%AC%AC%E4%B8%80%E6%AC%A1%E4%BD%BF%E7%94%A8Servlet(2).png)

```java
见具体代码，javaWebExercise
```



## servlet

### servlet处理参数中文乱码问题

```
tomcat8之前，设置编码：
      1)get请求方式：
        //get方式目前不需要设置编码（基于tomcat8）
        //如果是get请求发送的中文数据，转码稍微有点麻烦（tomcat8之前）
        String fname = request.getParameter("fname");
        //1.将字符串打散成字节数组
        byte[] bytes = fname.getBytes("ISO-8859-1");
        //2.将字节数组按照设定的编码重新组装成字符串
        fname = new String(bytes,"UTF-8");
      2)post请求方式：
        request.setCharacterEncoding("UTF-8");
         tomcat8开始，设置编码，只需要针对post方式
        request.setCharacterEncoding("UTF-8");
    注意：
        需要注意的是，设置编码(post)这一句代码必须在所有的获取参数动作之前
```









### Servlet的继承关系 - 重点查看的是服务方法（service()）

#### 1. 继承关系

  javax.servlet.Servlet接口
          javax.servlet.GenericServlet抽象类
              javax.servlet.http.HttpServlet抽象子类（最小，继承上一个）





####  2. 相关方法

```java
javax.servlet.Servlet接口:
        void init(config) - 初始化方法
        void service(request,response) - 服务方法
        void destory() - 销毁方法

      javax.servlet.GenericServlet抽象类：
        void service(request,response) - 仍然是抽象的

      javax.servlet.http.HttpServlet 抽象子类：
        void service(request,response) - 不是抽象的
            
        //1. String method = req.getMethod(); 获取请求的方式
        //2. 各种if判断，根据请求方式不同，决定去调用不同的do方法
            if (method.equals("GET")) {
                this.doGet(req,resp);
            } else if (method.equals("HEAD")) {
                this.doHead(req, resp);
            } else if (method.equals("POST")) {
                this.doPost(req, resp);
            } else if (method.equals("PUT")) {
        //3. 在HttpServlet这个抽象类中，do方法都差不多:
        protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
            String protocol = req.getProtocol();
            String msg = lStrings.getString("http.method_get_not_supported");
            if (protocol.endsWith("1.1")) {
                resp.sendError(405, msg);
            } else {
                resp.sendError(400, msg);
            }
        }
            
        //报405，子类无doGet 调用父类的doGet 报405和msg
```





#### 3.小结

```
1、继承关系： HttpServlet -> GenericServlet -> Servlet

2、Servlet中的核心方法： init() , service() , destroy()

3、服务方法： 当有请求过来时，service方法会自动响应（其实是tomcat容器调用的）

​      在HttpServlet中我们会去分析请求的方式：到底是get、post、head还是delete等等
​      然后再决定调用的是哪个do开头的方法
​      那么在HttpServlet中这些do方法默认都是405的实现风格-要我们子类去实现对应的方法，否则默认会报405错误

4、因此，我们在新建Servlet时，我们才会去考虑请求方法，从而决定重写哪个do方法
```









### Servlet的生命周期

​    

```
    1） 生命周期：从出生到死亡的过程就是生命周期。对应Servlet中的三个方法：init(),service(),destroy()
    2） 默认情况下：
        第一次接收请求时，这个Servlet会进行实例化(调用构造方法)、初始化(调用init())、然后服务(调用service())
        从第二次请求开始，每一次都是服务
        当容器关闭时，其中的所有的servlet实例会被销毁，调用销毁方法
    3） 通过案例我们发现：
        - Servlet实例tomcat只会创建一个，所有的请求都是这个实例去响应。
        - 默认情况下，第一次请求时，tomcat才会去实例化，初始化，然后再服务.这样的好处是什么？ 提高系统的启动速度 。 这样的缺点是什么？ 第一次请求时，耗时较长。
        - 因此得出结论： 如果需要提高系统的启动速度，当前默认情况就是这样。如果需要提高响应速度，我们应该设置Servlet的初始化时机。
    4） Servlet的初始化时机：
        - 默认是第一次接收请求时，实例化，初始化
        - 我们可以通过<load-on-startup>来设置servlet启动的先后顺序,数字越小，启动越靠前，最小值0
    5） Servlet在容器中是：单例的、线程不安全的
        - 单例：所有的请求都是同一个实例去响应
        - 线程不安全：一个线程需要根据这个实例中的某个成员变量值去做逻辑判断。但是在中间某个时机，另一个线程改变了这个成员变量的值，从而导致第一个线程的执行路径发生了变化
        - 我们已经知道了servlet是线程不安全的，给我们的启发是： 尽量的不要在servlet中定义成员变量。如果不得不定义成员变量，那么不要去：①不要去修改成员变量的值 ②不要去根据成员变量的值做一些逻辑判断

```



![image-20220711162629500](https://shj-img.oss-cn-beijing.aliyuncs.com/img/image-20220711162629500.png)

​                                       会使得启动Tomcat时就进行了初始化，开始项目直接进入服务



#### 线程不安全

![image-20220712075752344](https://shj-img.oss-cn-beijing.aliyuncs.com/img/image-20220712075752344.png)





### Http协议

```
    详细内容见代码重工
    1） Http称之为超文本传输协议
    2） Http是无状态的
    3） Http请求响应包含两个部分：请求和响应
    
      - 请求：
        请求包含三个部分： 1.请求行 ； 2.请求消息头 ； 3.请求主体
        1)请求行包含是三个信息： 1. 请求的方式 ； 2.请求的URL ； 3.请求的协议（一般都是HTTP1.1）
        2)请求消息头中包含了很多客户端需要告诉服务器的信息，比如：我的浏览器型号、版本、我能接收的内容的类型、我给你发的内容的类型、内容的长度等等
        3)请求体，三种情况
          get方式，没有请求体，但是有一个queryString
          post方式，有请求体，form data
          json格式，有请求体，request payload
          
          
      - 响应：
        响应也包含三本： 1. 响应行 ； 2.响应头 ； 3.响应体
        1)响应行包含三个信息：1.协议 2.响应状态码(200) 3.响应状态(ok)
        2)响应头：包含了服务器的信息；服务器发送给浏览器的信息（内容的媒体类型、编码、内容长度等）
        3)响应体：响应的实际内容（比如请求add.html页面时，响应的内容就是<html><head><body><form....）
```





### 会话

```
    1） Http是无状态的
        - HTTP 无状态 ：服务器无法判断这两次请求是同一个客户端发过来的，还是不同的客户端发过来的
        - 无状态带来的现实问题：第一次请求是添加商品到购物车，第二次请求是结账；如果这两次请求服务器无法区分是同一个用户的，那么就会导致混乱
        - 通过会话跟踪技术来解决无状态的问题。

    2） 会话跟踪技术
        - 客户端第一次发请求给服务器，服务器获取session，获取不到，则创建新的，然后响应给客户端
        - 下次客户端给服务器发请求时，会把sessionID带给服务器，那么服务器就能获取到了，那么服务器就判断这一次请求和上次某次请求是同一个客户端，从而能够区分开客户端
        - 常用的API：
          request.getSession() -> 获取当前的会话，没有则创建一个新的会话
          request.getSession(true) -> 效果和不带参数相同
          request.getSession(false) -> 获取当前会话，没有则返回null，不会创建新的

          session.getId() -> 获取sessionID
          session.isNew() -> 判断当前session是否是新的
          session.getMaxInactiveInterval() -> session的非激活间隔时长，默认1800秒
          session.setMaxInactiveInterval()
          session.invalidate() -> 强制性让会话立即失效
          ....

    3） session保存作用域
      - session保存作用域是和具体的某一个session对应的
      - 常用的API：
        void session.setAttribute(k,v)
        Object session.getAttribute(k)
        void removeAttribute(k)
```

![image-20220712082913325](https://shj-img.oss-cn-beijing.aliyuncs.com/img/image-20220712082913325.png)

```java
package com.atguigu.servlets;

import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import javax.servlet.http.HttpSession;
import java.io.IOException;

//演示Session
public class Demo03Servlet extends HttpServlet {
    @Override
    protected void service(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //获取session,如果获取不到，则创建一个新的
        HttpSession session = request.getSession() ;
        System.out.println("session ID : " + session.getId());

    }
}
//返回session ID为5AE3
```

```html
//web中配置环境
<servlet>
        <servlet-name>Demo03Servlet</servlet-name>
        <servlet-class>com.atguigu.servlets.Demo03Servlet</servlet-class>
</servlet>

<servlet-mapping>
        <servlet-name>Demo03Servlet</servlet-name>
        <url-pattern>/demo03</url-pattern>
</servlet-mapping>
```



#### session保存作用域

![image-20220712090545428](https://shj-img.oss-cn-beijing.aliyuncs.com/img/image-20220712090545428.png)

下面那个Session ID与上面的不同，无法调用上面ID创建保存的数据(另一个浏览器则无法调用)



### 服务器内部转发以及客户端重定向

```
    
    1） 服务器内部转发 : request.getRequestDispatcher("...").forward(request,response);
      - 一次请求响应的过程，对于客户端而言，内部经过了多少次转发，客户端是不知道的
      - 地址栏没有变化
      
    2） 客户端重定向： response.sendRedirect("....");
      - 两次请求响应的过程。客户端肯定知道请求URL有变化
      - 地址栏有变化

```

#### 服务器内部转发 

![image-20220712103044914](https://shj-img.oss-cn-beijing.aliyuncs.com/img/image-20220712103044914.png)



#### 客户端重定向

![image-20220712103139191](https://shj-img.oss-cn-beijing.aliyuncs.com/img/image-20220712103139191.png)



### Thymeleaf - 视图模板技术

![06.水果库存系统首页实现思路](https://shj-img.oss-cn-beijing.aliyuncs.com/img/06.%E6%B0%B4%E6%9E%9C%E5%BA%93%E5%AD%98%E7%B3%BB%E7%BB%9F%E9%A6%96%E9%A1%B5%E5%AE%9E%E7%8E%B0%E6%80%9D%E8%B7%AF.png)

```
    1） 添加thymeleaf的jar包
    2） 新建一个Servlet类ViewBaseServlet （代码重工）
    3） 在web.xml文件中添加配置
       - 配置前缀 view-prefix
       - 配置后缀 view-suffix(与ViewBaseServlet中代码有关)
    4） 使得我们的Servlet继承ViewBaseServlet

    5） 根据逻辑视图名称 得到 物理视图名称
    //此处的视图名称是 index
    //那么thymeleaf会将这个 逻辑视图名称 对应到 物理视图 名称上去
    //逻辑视图名称 ：   index
    //物理视图名称 ：   view-prefix + 逻辑视图名称 + view-suffix
    //所以真实的视图名称是：      /       index       .html
    super.processTemplate("index",request,response);
    6） 使用thymeleaf的标签
      th:if   ,  th:unless   , th:each   ,   th:text
```

// 200 : 正常响应
// 404 : 找不到资源
// 405 : 请求方式不支持
// 500 : 服务器内部错误

#### 渲染index界面- 使用thymeleaf的标签

```html
<tr th:if="${#lists.isEmpty(session.fruitList)}">
     <td colspan="4">对不起，库存为空！</td> 
</tr>
                   
<tr th:unless="${#lists.isEmpty(session.fruitList)}" th:each="fruit : ${session.fruitList}">
   <td th:text="${fruit.fname}">苹果</td>
   <td th:text="${fruit.price}">5</td>
   <td th:text="${fruit.fcount}">20</td>
   <td><img src="imgs/del.jpg" class="delImg"/></td>
</tr>

--${#lists.isEmpty()} 判断是否为空
--访问域对象，操作对话域 从session中取数据#lists.isEmpty(session.fruitList)
--分支迭代 让标记了th:if、th:unless的标签根据条件决定是否显示。
--循环迭代  th:each
--th:each="fruit : ${session.fruitList}" 循环一次就将fruitList中的数据传送到fruit中
--th:text：设置td中的内部文本
```

##### review:

D:\Java\javaweb\尚硅谷JavaWeb2022版全新教程\代码素材资料\Day5-thymeleaf-fruit\代码\pro10-fruit1.5-thymeleaf  readme   



### servlet保存作用域

```
1. 保存作用域
   原始情况下，保存作用域我们可以认为有四个： page（页面级别，现在几乎不用） , request（一次请求响应范围） , session（一次会话范围） , application（整个应用程序范围）
   1） request：一次请求响应范围
   2） session：一次会话范围有效
   3） application： 一次应用程序范围有效
```

#### request保存作用域

![01.Request保存作用域](https://shj-img.oss-cn-beijing.aliyuncs.com/img/01.Request%E4%BF%9D%E5%AD%98%E4%BD%9C%E7%94%A8%E5%9F%9F.png)

上图请求2获取不到请求1的数据 

**request.setAttribute是在请求域里面加了一个请求的参数，所以在sendRedirect以后是无法取到request.setAttribute的请求的**

下图内部调整，是一次性响应，可以得到数据





#### Session保存作用域

![02.Session保存作用域](https://shj-img.oss-cn-beijing.aliyuncs.com/img/02.Session%E4%BF%9D%E5%AD%98%E4%BD%9C%E7%94%A8%E5%9F%9F.png)

浏览器开启到关闭，数据只和浏览器关闭有关系

##### 钝化与活化

[Session 的钝化与活化_留兰香丶的博客-CSDN博客_session的钝化和活化](https://blog.csdn.net/codejas/article/details/79041006)

```java
@WebServlet("/demo03")
public class Demo03Servlet extends HttpServlet {
    @Override
    protected void service(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //1.向session保存作用域保存数据
        request.getSession().setAttribute("uname","lili");
        //2.客户端重定向
        response.sendRedirect("demo04");

        //3.服务器端转发
        //request.getRequestDispatcher("demo04").forward(request,response);
    }
}


@WebServlet("/demo04")
public class Demo04Servlet extends HttpServlet {
    @Override
    protected void service(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //1.获取session保存作用域保存的数据，key为uname
        Object unameObj = request.getSession().getAttribute("uname");
        System.out.println("unameObj = " + unameObj);
    }
}
```



#### Application保存作用域

![03.Application保存作用域](https://shj-img.oss-cn-beijing.aliyuncs.com/img/03.Application%E4%BF%9D%E5%AD%98%E4%BD%9C%E7%94%A8%E5%9F%9F.png)

服务器开启到关闭

```java
//演示application保存作用域（demo05和demo06）
@WebServlet("/demo05")
public class Demo05Servlet extends HttpServlet {
    @Override
    protected void service(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //1.向application保存作用域保存数据
        //ServletContext : Servlet上下文
        ServletContext application = request.getServletContext();
        application.setAttribute("uname","lili");
        //2.客户端重定向
        response.sendRedirect("demo06");

        //3.服务器端转发
        //request.getRequestDispatcher("demo04").forward(request,response);
    }
}

@WebServlet("/demo06")
public class Demo06Servlet extends HttpServlet {
    @Override
    protected void service(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //1.获取application保存作用域保存的数据，key为uname
        ServletContext application = request.getServletContext() ;
        Object unameObj = application.getAttribute("uname");
        System.out.println("unameObj = " + unameObj);
    }
}

```



### servlet路径问题

![04.相对路径_绝对路径_base标签_@{}1](https://shj-img.oss-cn-beijing.aliyuncs.com/img/04.%E7%9B%B8%E5%AF%B9%E8%B7%AF%E5%BE%84_%E7%BB%9D%E5%AF%B9%E8%B7%AF%E5%BE%84_base%E6%A0%87%E7%AD%BE_@%7B%7D1.png)

红色是相对路径 蓝色为绝对路径



### 项目实战

```html
1、编辑和修改库存信息 <td><a th:text="${fruit.fname}" th:href="@{/edit.do(fid=${fruit.fid})}">苹果</a></td>  --设置超链接方法 @{/edit.do}为绝对路径  "@{'/edit.do?fid='+${fruit.fid}}"写法是一部分字符串需要th:href去解析

常规写法/edit.do(fid=${fruit.fid})  /edit.do为常规部分 
(fid=${fruit.fid}) 一个name等于一个value值 

eg:(fid=${fruit.fid},fname=${})


<td th:text="${fruit.price}">5</td>
<td th:text="${fruit.fcount}">20</td>


2、<td><a th:text="${fruit.fname}" th:href="@{'/edit.do?fid='+${fruit.fid}}">苹果</a></td> --加超链接

<td><a th:text="${fruit.fname}" th:href="@{/edit.do(fid=${fruit.fid})}">苹果</a></td>  -- 最终写法
```





## MVC-Servlet优化   

#### 之前的servlet 



![01.mvc01](https://shj-img.oss-cn-beijing.aliyuncs.com/img/01.mvc01.png)

#### 优化后的

![02.mvc02](https://shj-img.oss-cn-beijing.aliyuncs.com/img/02.mvc02.png)

```java
//合并成一块
@WebServlet("/fruit.do")
public class FruitServlet extends ViewBaseServlet {
    private FruitDAO fruitDAO = new FruitDAOImpl();

    @Override
    protected void service(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //设置编码
        request.setCharacterEncoding("UTF-8");

        String operate = request.getParameter("operate");
        if(StringUtil.isEmpty(operate)){
            operate = "index" ;
        }

        switch(operate){
            case "index":
                index(request,response);
                break;
            case "add":
                add(request,response);
                break;
            case "del":
                del(request,response);
                break;
            case "edit":
                edit(request,response); 
                break;
            case "update":
                update(request,response);
                break;
            default:
                throw new RuntimeException("operate值非法!");
        }
    }

    private void update(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //1.设置编码
        request.setCharacterEncoding("utf-8");

        //2.获取参数
        String fidStr = request.getParameter("fid");
        Integer fid = Integer.parseInt(fidStr);
        String fname = request.getParameter("fname");
        String priceStr = request.getParameter("price");
        int price = Integer.parseInt(priceStr);
        String fcountStr = request.getParameter("fcount");
        Integer fcount = Integer.parseInt(fcountStr);
        String remark = request.getParameter("remark");

        //3.执行更新
        fruitDAO.updateFruit(new Fruit(fid,fname, price ,fcount ,remark ));

        //4.资源跳转
        //super.processTemplate("index",request,response);
        //request.getRequestDispatcher("index.html").forward(request,response);
        //此处需要重定向，目的是重新给IndexServlet发请求，重新获取furitList，然后覆盖到session中，这样index.html页面上显示的session中的数据才是最新的
        response.sendRedirect("fruit.do");
    }

    private void edit(HttpServletRequest request , HttpServletResponse response)throws IOException, ServletException {
        String fidStr = request.getParameter("fid");
        if(StringUtil.isNotEmpty(fidStr)){
            int fid = Integer.parseInt(fidStr);
            Fruit fruit = fruitDAO.getFruitByFid(fid);
            request.setAttribute("fruit",fruit);
            super.processTemplate("edit",request,response);
        }
    }

    private void del(HttpServletRequest request , HttpServletResponse response)throws IOException, ServletException {
        String fidStr = request.getParameter("fid");
        if(StringUtil.isNotEmpty(fidStr)){
            int fid = Integer.parseInt(fidStr);
            fruitDAO.delFruit(fid);

            //super.processTemplate("index",request,response);
            response.sendRedirect("fruit.do");
        }
    }

    private void add(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        request.setCharacterEncoding("UTF-8");

        String fname = request.getParameter("fname");
        Integer price = Integer.parseInt(request.getParameter("price")) ;
        Integer fcount = Integer.parseInt(request.getParameter("fcount"));
        String remark = request.getParameter("remark");

        Fruit fruit = new Fruit(0,fname , price , fcount , remark ) ;

        fruitDAO.addFruit(fruit);

        response.sendRedirect("fruit.do");

    }

    private void index(HttpServletRequest request , HttpServletResponse response)throws IOException, ServletException {
        HttpSession session = request.getSession() ;

        // 设置当前页，默认值1
        Integer pageNo = 1 ;

        String oper = request.getParameter("oper");

        //如果oper!=null 说明 通过表单的查询按钮点击过来的
        //如果oper是空的，说明 不是通过表单的查询按钮点击过来的
        String keyword = null ;
        if(StringUtil.isNotEmpty(oper) && "search".equals(oper)){
            //说明是点击表单查询发送过来的请求
            //此时，pageNo应该还原为1 ， keyword应该从请求参数中获取
            pageNo = 1 ;
            keyword = request.getParameter("keyword");
            //如果keyword为null，需要设置为空字符串""，否则查询时会拼接成 %null% , 我们期望的是 %%
            if(StringUtil.isEmpty(keyword)){
                keyword = "" ;
            }
            //将keyword保存（覆盖）到session中
            session.setAttribute("keyword",keyword);
        }else{
            //说明此处不是点击表单查询发送过来的请求（比如点击下面的上一页下一页或者直接在地址栏输入网址）
            //此时keyword应该从session作用域获取
            String pageNoStr = request.getParameter("pageNo");
            if(StringUtil.isNotEmpty(pageNoStr)){
                pageNo = Integer.parseInt(pageNoStr);   //如果从请求中读取到pageNo，则类型转换。否则，pageNo默认就是1
            }
            //如果不是点击的查询按钮，那么查询是基于session中保存的现有keyword进行查询
            Object keywordObj = session.getAttribute("keyword");
            if(keywordObj!=null){
                keyword = (String)keywordObj ;
            }else{
                keyword = "" ;
            }
        }

        // 重新更新当前页的值
        session.setAttribute("pageNo",pageNo);

        FruitDAO fruitDAO = new FruitDAOImpl();
        List<Fruit> fruitList = fruitDAO.getFruitList(keyword , pageNo);
        session.setAttribute("fruitList",fruitList);

        //总记录条数
        int fruitCount = fruitDAO.getFruitCount(keyword);
        //总页数
        int pageCount = (fruitCount+5-1)/5 ;
        /*
        总记录条数       总页数
        1               1
        5               1
        6               2
        10              2
        11              3
        fruitCount      (fruitCount+5-1)/5
         */
        session.setAttribute("pageCount",pageCount);

        //此处的视图名称是 index
        //那么thymeleaf会将这个 逻辑视图名称 对应到 物理视图 名称上去
        //逻辑视图名称 ：   index
        //物理视图名称 ：   view-prefix + 逻辑视图名称 + view-suffix
        //所以真实的视图名称是：      /       index       .html
        super.processTemplate("index",request,response);
    }
}

```



#### switch优化

```java
@Override
    protected void service(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //设置编码
        request.setCharacterEncoding("UTF-8");

        String operate = request.getParameter("operate");
        if(StringUtil.isEmpty(operate)){
            operate = "index" ;
        }
        
        Method[] methods=this.getClass().getDeclaredMethods();
        for(Method m:methods){
            String methodName=m.getName();
            if(operate.equals(methodName)){
              try{
                  //找到和operate同名的方法，通过反射技术调用它
                m.invoke(this,request,response);
                return;
                  
              } catch(IllegalAccessException e){
                  e.printStackTrace
              } catch(InvocationTargetException e){
                  e.printStackTrace();
              }
                
            }
        }
        throw new RuntimeException("operate值非法!");
        }
    }
```



#### 中央控制器

![03.MVC03](https://shj-img.oss-cn-beijing.aliyuncs.com/img/03.MVC03.png)

见pro15 



1、根据请求的url获取servletPath，根据servletPath去解析截取字符串，解析出一个名字

2、解析加载配置文件applicationContext.xml， 从配置文件中读取每一个bean扔到beanMap文件中

3、根据得到servletPath得到的名字去beanMap中找到能够处理类controller,调用controller类对应的方法，具体方法有object值来决定







Maven配置

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.shj</groupId>
  <artifactId>Maven02</artifactId>
  <packaging>war</packaging>
  <version>1.0-SNAPSHOT</version>
  <name>Maven02 Maven Webapp</name>
  <url>https://maven.apache.org</url>

  <!-- JDN的版本修改为11 -->
  <properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <maven.compiler.source>1.8</maven.compiler.source>
    <maven.compiler.target>1.8</maven.compiler.target>
  </properties>

  <dependencies>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.13.2</version>
      <scope>test</scope>
    </dependency>
  </dependencies>

  <build>
    <finalName>maven03</finalName>
    <plugins>
      <plugin>
        <groupId>org.eclipse.jetty</groupId>
        <artifactId>jetty-maven-plugin</artifactId>
        <version>9.4.11.v20180605</version>
        <configuration>
          <!-- 热部署，每10s扫描一次 -->
          <scanIntervalSeconds>10</scanIntervalSeconds>
          <!-- 可指定当前项目的站点名 -->
          <webApp>
            <contextPath>/maven03</contextPath>
          </webApp>
          <httpConnector>
            <port>8090</port> <!-- 端口号 -->
          </httpConnector>
        </configuration>
      </plugin>
      <!-- 设置在plugins标签中 -->
      <plugin>
        <groupId>org.apache.tomcat.maven</groupId>
        <artifactId>tomcat7-maven-plugin</artifactId>
        <version>2.1</version>
        <configuration>
          <port>8081</port> <!-- 启动端口 默认:8080 -->
          <path>/test</path> <!-- 项目的站点名，即对外访问路径 -->
          <uriEncoding>UTF-8</uriEncoding> <!-- 字符集编码 默认：ISO-8859-1 -->
          <server>tomcat7</server> <!-- 服务器名称 -->
        </configuration>
      </plugin>
    </plugins>
  </build>
</project>

```

