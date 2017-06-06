# 欢迎访问我的 开发报告

------

我将从以下几个方面向读者展示我的开发报告

> * 策划思路
> * 页面结构与说明
> * 技术指标
> * 技术点说明
> * 开发心得

![cmd-markdown-logo](https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1496201399228&di=f03b3821d542b740ec1e3b05d3abd722&imgtype=0&src=http%3A%2F%2Fwww.qq745.com%2Fuploads%2Fallimg%2F140928%2F1-14092PRS5-52.jpg)

## 策划思路：

> Web课程最终考核需要提交一个个人网站，我是一个《柯南》的忠实粉丝，自然想到了做一个简单的柯南介绍的站点。为了避免俗套，我特别添加了该作品的反面评价，让大家能更深层次的理解这部动漫。<br><br>
希望通过我在站点的介绍，让没看过这部动漫的同学了解这样一动漫部甚至对这部动漫产生兴趣，让看过这部动漫的读者对该动漫作品有更深层次的理解。<br><br>
对于站点的内容，主要来自贴吧，百科，百度云盘，知乎。


------

## 页面结构与说明

我这次的站点由五个小网页组成，分别为：首页（home.html），剧场版资源页（ziyuan.html），最吓人页（xiaren.html），主线人物页（people.html），关于&联系我页（个人简历.html）。这五个小页面用标题栏的形式在每个页面的顶部展示，方便读者任意切换。<br><br>
home.html（此页面作为首页和列表页）：     罗列了许多关于《柯南》不得不说的事，包括“动漫简介”“作品的社会评价”“动漫和原作漫画的区别”。另外，引入了几个极具争议的话题，放在右下键的资源链接框。<br><br>
ziyuan.html（此页面作为详细页）：《柯南》动漫中最受观众喜欢的可以说是其完整的剧场版了，比起有点让人摸不着头脑的TV版资源，剧场版的被关注程度要大很多。我在这个界面用了一个小小的JS图片切换和一个浮动栏。<br><br>
xiaren.html（此页面作为列表页和详细页）：作为一部侦探题材的动漫，《柯南》自然有一些阴森恐怖的剧集，我在这个页面简单介绍了一些我认为比较吓人的TV版剧集，以及一个网页视频地址。<br><br>
people.html（此页面作为表单页和列表页）：很多只看过几集《柯南》的人会以为柯南只是无数个小案件构成的，实际不然，它有一个贯穿整部动漫的大剧情，俗称为“柯南剧情篇”，这里的主线人物就是“剧情篇”中的人物。<br><br>
个人简历.html（此页面作为详细页）：这其实是我的首次HTML作业，放在这里是方便有兴趣的读者可以找到我，页面中的个人QQ主页可以访问我的QQ空间，有个邮箱地址，点击就可以直接给我发邮件。

------

## 技术指标

- [x] 兼容的浏览器版本：最新版火狐，IE9，Edge以及最新版本的各大浏览器
- [x] 所使用的html/css版本：主要代码是html5以及css3
- [x] 开发工具（浏览器、编辑器及其它工具）：Sublime Text（编辑器），Edge（浏览器），ps（其他）
- [x] 说明：所有的css和html代码都是自己打上的，用Photoshop给一些图片缩小了像素大小

------

##技术点说明——技术难点
### 1. 标题栏的效果设置

> 这只一个放在页面顶部的标题栏，看起来是一个很简单的问题，用一个行内列表几行css代码就好了。
实际上在我第一次做出来以后我也觉得没问题，但是自己的笔记本和机房的电脑屏幕大小差别太大，导致了机房电脑显示出现问题，修改了以后，笔记本上的页面显示又出现了问题。
我开始意识到不能使用绝对定位，也不能使用固定像素。
最后把标题栏文字大小和line-height的单位都变成em，两边的距离left-margin等都用百分数表示，现在已经可以适应大多数尺寸的电脑。
遗留问题：手机移动端的屏幕尺寸更小，我所做的页面完全不能显示出来，到底怎样做出一个自适应的网页有待我的进一步学习。
局部css代码：
``#menu ul {list-style: none;	margin-left: 15%;}
     #menu ul li{
     display: inline;
	font-size: 2em;
	height: 2em;
	padding: 0.8em 1.2em 0.8em 1.2em;
	color: black;	
	text-decoration: none;
	text-align: center;
	font-family: 华文彩云;
    }
    #menu ul li a{text-decoration: none;color: black;}
    #menu ul li a:hover, #menu ul .now {color: #f59c0f;}``
局部html代码：
`` <div id="menu">
    <ul type="none;">
    <li><a href="home.html">首页</a></li>
    <li><a href="ziyuan.html">剧场版资源</a></li>
    <li><a href="xiaren.html" class="now">最吓人</a></li>
    <li><a href="people.html">主线人物</a></li>
    <li><a href="个人简历/个人简历.html">关于&联系我</a></li>
    </ul>
    </div> ``

### 2. 盒模型的放置问题
> 我在ziyuan.html,个人简介.html,xiaren.html这几个网页都用了盒模型，其中ziyuan,html用得少，没有出问题，但其他两个页面的问题就很大。
几个div盒子并没有按照我的意愿分布，而是这里一块那里一块，莫名其妙的空格，不明来历的重合，还有些盒子根本没有正常显示。
遇到这种问题我的第一想法是按照第一个问题的思路来。于是又去把字号改作em，又引进了float标签，却始终不凑效，还是有莫名其妙的空行，空格，不同大小的屏幕页面效果也有不同。
最后改进的方法是把部分的div标签换成span标签，做成一个即使有部分“错位”也对页面大局影响不大的网页。
局部代码：
``table{
	 background-color: #D5D5D5;
	 border:1px solid black ; 
	 margin-left: 20%;
	 width: 60%;
	 text-align: left;
}
table img{
	height: 200px;
	width: 150px;
}``
``.hezi1{
	background-color: gray;
	border: 2px solid black;
	margin-left: 20%;
	width: 50%;
	height: 500px;
}
.hezi1 img{
	margin-top: 0;
	float :right;
	height: 156px;
	width: 250px;
}
.hezi2{
	background-color: gray;
	border: 2px solid black;
	margin-left: 50%;
	width: 20%;
	height: 500px;
}``

### 3. video标签插入视频问题
> 我最开始想在xiaren.html里面放入一个video标签，链接一个自动播放的视频。
但考虑到视频文件太大，不合符作业的规定，我就在网上找了一下[查看页面视频原地址的方法]，并最终让我找到了，不过更大的问题也来了。网页上的原视频地址频繁刷新，一个小时前还能打开，一个小时后就找不到文件了，这是一个很麻烦的问题，你总不可能按时更改吧，不切实际。随后我尝试过几种方法固定原地址，比如自己转发去贴吧然后再引用贴吧地址，都不奏效。
最后解决这个问题的办法，实际上不算真的解决，我把视频文件换成了链接栏，必须离开我的网页才能看到视频。原网址也就变成了对几个恐怖剧情的介绍网址。

## 开发心得

### 1. 书写网页前的设计很重要，参考如下流程图

```flow
st=>start: 开始
op=>operation: 网页大致构思
cond=>condition: 构思完毕?
e=>end: 书写

st->op->cond
cond(yes)->e
cond(no)->op
```

### 2. 绘制网站框架作为辅助，引入[序列图](https://www.zybuluo.com/mdeditor?url=https://www.zybuluo.com/static/editor/md-help.markdown#8-序列图)

```seq
首页->详细页: 给我详细的资料！
Note right of 详细页: 序列图
详细页-->首页: 正在给你发送!
```
### 3. 合理利用网络资源
>各类html和css的模板或者资源，在各大网站都有，但是胡乱套用容易出问题，特别是JavaScript。为了更好地利用网络带宽，应该尽量使用小尺寸的图片，或者引用图片网址。

### 4. 项目回顾

| 项目        | 难度   |   用时/week |
| --------   | -----:  | :----:  |
| 必要知识学习     | harder |   10     |
| 首页     | hardest |   3     |
| 其他页面      |   hard   |   2   |
| 后期修改      |    easy    |  1  |
| 总体回顾      |    easy    |  16  |


------

再一次感谢您花费时间阅读这份开发报告！

作者 [@Melon-Seeds][4]     
2017 年 05月 31日    


