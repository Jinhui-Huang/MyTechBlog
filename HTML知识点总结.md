> 本篇文章由hjh整合, 打开 IDEA 用最适合你自己的编辑器来编写
<br>
<br>Markdown格式书写(用来专门写笔记和知识点的一种文本格式)
<br>Markdown完全支持HTML样式的书写
<!-- TOC -->
* [HTML第一天知识总结](#html第一天知识总结)
  * [一. 网络编程的三大基石：](#一-网络编程的三大基石)
  * [二. head 标签里常用的子标签：](#二-head-标签里常用的子标签)
    * [(1). charset="utf-8" 支持中文不乱码](#1-charsetutf-8-支持中文不乱码)
    * [(2). 页面的标题标签](#2-页面的标题标签)
    * [(3). 标题图标](#3-标题图标)
    * [(4). 重要标签](#4-重要标签)
  * [三. body标签里常用的子标签：](#三-body标签里常用的子标签)
    * [(1). 文本标签：](#1-文本标签)
    * [(2). 超链接标签： a](#2-超链接标签-a)
    * [(3). 超文本标签：](#3-超文本标签)
    * [(4). 列表标签：](#4-列表标签)
    * [(5). 表格标签：](#5-表格标签)
    * [(6). 表单标签：](#6-表单标签)
<!-- TOC -->

# HTML第一天知识总结

## 一. 网络编程的三大基石：

- **url 统一资源定位符 “网址”----网络之间的地址。**
    - https://www.baidu.com/img/PCtm_d9c8750bed0b3c7d089fa7d55720d6cf.png
    - url格式: `https://ip+端口/项目名?值`
      https://www.baidu.com/s?wd=mayun
    - uri格式: 统一资源标识符 ----本项目内地址
      `img/aa.png`

- **http1.1协议：===“交通法规”**
    - 三大特性:
    - 单向性 —— 网络之间通信 一定是先由客户端 向服务器发送请求，再由服务器给出响应。
    - 长链接 —— 一旦客户端与服务器建立连接之后，可以无限次发送请求 获得响应，直到客户端主动断开连接
    - 无状态 —— 服务器端 不进行数据的保存。 但是现在网络之间有的数据存储，是有对应的技术：Cookie ，session ，中间件等
- **html 超文本标签/标记语言**

## 二. head 标签里常用的子标签：

### (1). charset="utf-8" 支持中文不乱码

```html

<meta charset="utf-8"/>  
```

### (2). 页面的标题标签

```html
<title></title> 
```

### (3). 标题图标

```html

<link rel="icon"
      href="//gss0.bdstatic.com/5foIcy0a2gI2n2jgoY3K/static/fisp_static/common/img/favicon.ico"
      mce_href="../static/img/favicon.ico"
      type="image/x-icon">
```

### (4). 重要标签

```html

<style>
</style>

<script>
</script>

<base/>
```

## 三. body标签里常用的子标签：

### (1). 文本标签：

- 标题标签

```html
<h1>一级标题</h1>
<h2>一级标题</h2>
<h3>一级标题</h3>
<h4>一级标题</h4>
<h5>一级标题</h5>
<h6>一级标题</h6>
<b>加粗字体</b>
<i>倾斜字体</i>
<u>加下横线字体</u>
张<sub>三丰</sub>
张<sup>三丰</sup>
<abbr title="中国中央电视台">CCTV</abbr>
```

### (2). 超链接标签： a

作用：

- 页面之间跳转
    - 项目内 href="uri"
    - 项目外 href="url"   `http协议：//ip+端口/项目名/页面名`

```html
<a href="test1.html">链接文本</a>
<a href="http://www.baidu.com">点击跳转到百度</a>
```

- 页面之间跳转同时带值：
    - `uri/url?名字=值&名字=值&名字=值`

```html
<a href="https://www.baidu.com/s?wd=12306">跳转百度同时 查询“12306”</a>
<a href="https://www.so.com/s?q=12306">跳转360 同时 查询12306</a>
```
- 本页面内跳转：

`场合： 当前页面过长，可以通过a标签帮忙锁定位置。`              
```html
              
起跳位置：    <a href="#jdms">京东秒杀</a>
目的位置：    <a name="jdms"> 京东秒杀</a>
```
### (3). 超文本标签：
- 图片标签：
```html
<img src="图片的位置路径"
     alt="图片加载失败后，在图片的位置上显示的文字"
     title="鼠标悬浮的时候显示的文字"/>


<img src="img/aaa.png"
     alt="是一个企鹅"
     title="这是QQ"/>

<!-- img 设置图片的高和宽：
有两种方式设置：
（1）html方式： 属性名=属性值
（2）css方式：  Style="属性：属性值"（推荐）-->

```

- 音频，视频标签`<audio></audio>  <video></video>`

### (4). 列表标签：
- 无序列表：
```html
<ul type="square">你最喜欢的明星是：
	<li>刘德华</li>
	<li>刘德华</li>
	<li>刘德华</li>
	<li>刘德华</li>
	<li>刘德华</li>
</ul>
```
- 有序列表：
```html

<ol type="A">获得offer的步骤：
    <li>投递简历</li>
    <li>hr通知笔试时间</li>
    <li>第一轮技术面试</li>
    <li>第二轮人力资源面试</li>
    <li>下发offer</li>
</ol>
```
### (5). 表格标签：
- 制作普通的多行多列的表格
```html

<table border="1px" style="border-collapse: collapse;">
    <tr>
        <td>姓名</td>
        <td>年龄</td>
        <td>地址</td>
    </tr>
    <tr>
        <td>0000</td>
        <td>0000</td>
        <td>0000</td>
    </tr>
    <tr>
        <td>0000</td>
        <td>0000</td>
        <td>0000</td>
    </tr>
    <tr>
        <td>0000</td>
        <td>0000</td>
        <td>0000</td>
    </tr>
</table>
```

- 制作合并行，合并列  ，既合并行 又合并列的  表格
```html
<!--
	做题步骤：
	1.先确定表格里 行的数量
	2.载确定每行里 单元格的数量
	3.最后确定每个单元格的属性（跨行，跨列，既跨行又跨列，没属性）
 -->
<table border="1px" style="border-collapse: collapse;">
    <tr>
        <td colspan="2">姓名</td>
        <td>地址</td>
    </tr>
    <tr>
        <td>0000</td>
        <td>0000</td>
        <td rowspan="2">0000</td>
    </tr>
    <tr>
        <td rowspan="2" colspan="2">0000</td>
    </tr>
    <tr>
        <td>0000</td>
    </tr>
</table>
```
- 介绍表格其他项
```html
<!--制作1个5行3列的表格 -->
<table border="1px" style="border-collapse: collapse;">

    <caption>学生成绩单</caption>
    <thead>
    <tr>
        <td>000</td>
        <td rowspan="2">000</td>
        <td>000</td>
    </tr>
    <tr>
        <td>000</td>
        <td>000</td>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td>000</td>
        <td>000</td>
        <td>000</td>
    </tr>
    <tr>
        <td>000</td>
        <td>000</td>
        <td>000</td>
    </tr>
    </tbody>
    <tfoot>
    <tr>
        <td>000</td>
        <td>000</td>
        <td>000</td>
    </tr>
    </tfoot>
</table>
```
### (6). 表单标签：
- form标签：
  - action=“表单数据提交的位置” 
  - method="表单数据提交的方式"
  - **get**：相对来说不安全（提交的数据直接显示浏览器的地址栏里） 
    - 传递的数据信息长度有要求 
    - 传递的数据信息有类型要求，只能是文本 
    - 有缓存功能 “幂等” 
    - 各大浏览器统一使用get提交方式 
    - 支持cookie
  - **post**：相对来说安全 
    - 传递的数据信息几乎没要求（数据信息打成数据包的形式传递） 
    - 传递的数据信息没有类型要求。 
    - 没有缓存功能 
    - 不支持cookie
		
- 介绍表单元素：
  - **文本框：**  `<input />`
    - type="text" 设置表单元素类型 
    - name="wd"  存储用户输入的信息  **重要** 
    - placeholder="显示提示信息"
    - value="12306" 表单元素的默认值 
    - maxlength="6" 限制用户输入的信息长度
					
  - **密码框:**
    - type="password"
    - name="pwd" 
  - **单选按钮:**
    - type="radio" 设置表单元素类型为 单选按钮 
    - name="sex"   设置表单元素的名字， 
    - value="1"
    - id="woman"
    - checked  设置表单元素 默认选中
  - **复选框：**
  - type="checkbox"
  - name="citys"
  - value="sy"
  - checked
  - **下拉列表：** 
```html
<select name="year">
    <option value="2002" selected>2002</option>
</select><br/>
```
  - **文件域：**
    - type="file"
    - name="fileName"
    - `使用场合：文件的上传 下载操作`
				
  - **文本域：**
```html
<textarea name="areaName"
          readonly="readonly"
          style="height: 100px; width: 200px;resize: none;">
					欢迎使用本产品，请遵守平台规定！
</textarea>    
```

  - **隐藏域：**
    - type="hidden"
    - name="tn"
    - value="baiduhome_pg"

  - **重置按钮，提交按钮，普通按钮（常用） 图片按钮**
```html
<input type="reset" value="重置按钮" />
<input 
	type="button" 
	value="点我一下" 
onclick="JavaScript:alert('点我干嘛！')" />
<input type="image" src="../img/aa.png" title="我真的是图片"/>
<input type="submit" value="百度一下"/>	
```
				

  - **H5 新表单标签：**
```html
颜色盘：<input type="color" name="colors" />
时间控件：<input type="date" name="dt" />
月份控件：<input type="month" name="mon" />
星期控件：<input type="week" name="wee" />
邮箱：<input type="email" name="email" />
```









