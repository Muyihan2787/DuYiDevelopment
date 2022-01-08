[toc]
# 课程概述
__HTML__：Hyper Text Markup Language 超文本标记语言，定义网页内容结构。
__CSS__：Cascading Style Sheets 层叠样式表，定义网页内容样式。
**Javascript**：基于原型编程、多范式的动态脚本语言，定义网页内容行为。

1. 难度：对比所有的开发技术，HTML & CSS最简单。
2. 学习要点：
- 心态平和，忌浮躁
- 多练习，练习时间 > 听课
3. 软件开发行业分类：工科

MarkDown：文档格式标准。只关注内容，已设定好格式。（"#"，音类sharp，是一个音乐符号，不读井号）

# HTML和CSS概述
1. 术语：
- web：互联网
- w3c：万维网联盟，定义web标准，非盈利性组织,官网w3.org
- XML：可扩展的标记语言：extension markup language，用于定义文档结构的语言。
2. 什么是HTML、CSS？
HTML是W3C组织定义的语言标准：HTML是用于描述页面内容结构的语言
CSS是W3C组织定义的语言标准：CSS是用于描述页面内容样式的语言

3. 知识检索途径推荐：
+ 标准起草官方网站[w3.org](https://www.w3.org/)  纯英文
+ [MDN](https://developer.mozilla.org/zh-CN/docs/Learn)属于Mozilla Development Network，Mozilla开发者社区，支持中文。

4. 浏览器：
- shell：外壳
- core：内核（JS执行引擎、渲染引擎）
- 主流独立内核浏览器：**IE、Firefox、chrome、safari、opera**（内核见下）
- IE：Trident
- Firefox：Gecko
- chrome：webkit/Blink(现在使用的是这个)
- safari：webkit
- Opera：Presto/Blink(现在使用的是这个)

5. 目前演进标准版本：HTML5（2014年）、CSS3目前还没有完成制订。XHTML：可以认为是HTML的一个严格版本，完全符合XML的规范，作为历史了解即可。
# 第一个网页
 
## 常用插件
            vscode-icons
            live sever
            Markdown Preview Enhance
            Emmet插件：自动生成HTML代码片段，vscode内置插件，无需安装。

## 插入图片方法
先复制图片，再在md文档中按下ALT+CTRL+V实现插入

## 注释
为阅读者提供信息，不运行。
HTML注释格式：
<!-- ```号后面写文件后缀名 -->
```html
    <!-- 注释内容，此处可直接换行写多行 -->
```
```js
    var i = 2;
```
快捷键注释/取消注释：CTRL+/

## 元素
```html
<!-- 下面各行官方名称叫：元素(element) -->
<a href="http://www.baidu.com">baidu</a>
<title>Document</title>
```
大家也称它标签、标记

元素 = 起始标记(begin tag) + 结束标记(end tag) +元素内容 + 元素属性
- 区分大小写，起始元素名需相同

- 元素内容：往往是你要显示的东西，不同元素有不同的功能
- 元素属性：描述这个元素的额外属性(ref:reference)

有些元素没有结束标记，这样的元素叫做**空元素**，如meta,src。
空元素有两种写法：
1.```<meta charset="UTF-8">```
2.```<meta charset="UTF-8"/>```

属性 = 属性名 + 属性值
- 局部属性：某些元素特有的属性
- 全局属性：所有元素通用

## 元素嵌套
元素内容里再建立元素（注意：元素不能相互嵌套）
- 父元素：元素的邻上层元素
- 子元素：元素的邻下层元素
- 兄弟元素：有同一个父元素的元素
- 祖先元素：元素的所有上层元素
- 后代元素：元素的虽有下层元素

## 标准的文档结构

HTML页面：也叫HTML文档，具有一定格式要求。
**文档声明**：
```html
<!-- 以下是文档声明(特殊地它不是元素)，告诉浏览器，当前页面文档使用的HTML标准是THML5 -->
<!DOCTYPE html>
<!-- 不写文档声明，将导致浏览器进入怪异渲染模式 -->
```
**根元素**：一个页面最多只能一个，并且该元素是所有其他元素的父元素或祖先元素
```html
<!-- 以下是根元素，HTML5不强制写，但强烈建议 -->
<html lang="en">
<!-- 该元素有一个lang属性表示语言，是全局属性，表示该元素内部使用的是哪种自然语言书写而成的 -->
```
**元素lang属性**：
- en:英语
- zh-CN:简体中文，已过时
- cmn-hans:直译‘中国大陆官方用语-简体汉语’，推荐用这种。
可以给某个具体的元素添加语言属性（如果其元素内容语言不同于文档其他整体）

**文档头**：文档头部内容，不会显示到页面上。比如脑里想的东西别人是看不见的。
```html
<!-- 以下是文档头 -->
<head>
    <meta ATTR_name=xxx>:meta空元素，文档的元数据：告诉浏览器附加信息。
    <meta charset="UTF-8">：charset属性：字符集，指示网页以UTF-8编码方式(UTF,万国码)编码
    <meta name="viewport" content="width=device-width,initial-scale=1.0">：把网页视口的宽度设置为设备宽度。并初始化。
    viewport：网页的视口
    content：网页内容
    <meta http-equiv="X-UA-Compatible" content="ie=edge">：告诉浏览器如果使用IE浏览器内核建议使用edge内核。
    <title>Document</title>：网页标题。
    ······
</head>
```

**文档体**：页面所有要参与显示的元素全放在文档体里面。
```html
<body>
    <!-- 以下放置所有显示元素 -->
    ······
</body>
```
元素名一般都小写。

## 本节代码 index.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width,initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
    <!-- 超链接 -->
    <a href="http://www.baidu.com">baidu</a>
    <h1 title="this is my first page">
        第一个页面
    </h1>
</body>
</html>
```