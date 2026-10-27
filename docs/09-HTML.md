---
title: "第11讲 HTML入门"
nav_order: 11
permalink: /09-HTML/
date: 2026-10-27
layout: default
---

# 《新媒体交互设计》——第9讲 HTML入门

---

2026.10.27

------

问题1：互联网时代我们通过什么来了解世界呢？

* Screen（屏幕）

问题2：屏幕有哪些？

* PC
* Pad
* Phone

<img src="https://gitee.com/featon/picture/raw/master/20261012143856540.png" alt="image-20230827081230498" style="zoom:50%;" />

<img src="https://gitee.com/featon/picture/raw/master/20261026104931792.png" alt="image-20230827083151584" style="zoom: 33%;" />

物理像素 = 逻辑像素 × 设备像素比（DPR）

- ‌**iPhone 4/4s**‌：物理像素640×960，逻辑320×480，DPR=2，PPI 326。
- ‌**iPhone 14 Pro**‌：物理像素1179×2556（面板标称1170×2532），逻辑393×852，DPR=3。
- ‌**15英寸MacBook Pro (Retina)**‌：物理像素2880×1800，逻辑1440×900，DPR=2，PPI 220。
- ‌**27英寸5K iMac**‌：物理像素5120×2880，逻辑2560×1440，DPR=2，PPI 218。‌‌

做前端或设计时，布局一律按逻辑像素写，不用管物理像素。但‌**图片资源**‌需按DPR提供@2x、@3x版本，否则在高分屏上会模糊。

问题3：屏幕中内容的形式？

* 网站
* 网页

* HTML：*HyperText Markup Language*

<img src="https://gitee.com/featon/picture/raw/master/20261026105325268.png" alt="image-20230827090321632" style="zoom:33%;" />

## 9.1 网站建设

一个标准化的网站建设流程，通常遵循以下七个核心阶段。

<img src="https://gitee.com/featon/picture/raw/master/20261026105723233.png" style="zoom: 36%;" />

> 第一阶段：需求分析与规划（地基阶段）
>
> * 这是最重要、也最容易被忽略的阶段。项目组会与您进行深入沟通，围绕我们上一篇文章提到的7个关键问题展开讨论，明确网站的目标、用户、功能范围和预算。最终会输出一份详细的《网站建设需求文档》和《项目进度规划表》，作为整个项目的蓝图和依据。
>
> 第二阶段：网站架构与交互设计（骨架阶段）
>
> * 在明确需求后，交互设计师会开始规划网站的“骨架”，即信息架构。这包括网站的栏目设置、页面层级关系、用户的操作流程（如如何从首页找到产品并完成咨询）。通常会制作一个线框图，它就像一个网站的“施工图纸”，清晰地标明了每个页面的功能布局，但暂不涉及色彩和具体图片。
>
> **第三阶段：视觉设计（外貌阶段）**
>
> * 在确认线框图后，UI设计师会开始进行视觉设计。他们会根据您的品牌VI系统，设计出1-2套核心页面（如首页、产品详情页）的最终效果图。这个效果图是“高保真”的，包含了最终的色彩、字体、图标、图片等所有视觉元素。您在这个阶段看到的，就是网站上线后样子。
>
> 第四阶段：前端开发与后端开发（建造阶段）
>
> * 当设计稿确认后，技术团队开始“施工”。前端工程师将设计稿还原为网页代码（HTML/CSS/JavaScript），确保它在各种浏览器和设备上都能完美显示。后端工程师则负责开发网站的后台管理系统、数据库和功能逻辑，让网站可以动起来。
>
> 第五阶段：测试与优化（验收阶段）
>
> * 网站开发完成后，将部署到测试服务器，进入全面的测试环节。测试包括功能测试（所有链接、表单、支付等功能是否正常）、兼容性测试（在不同浏览器和设备上是否正常）、性能测试（页面加载速度、服务器压力）以及安全测试。所有发现的BUG和问题都会被记录并修复。
>
> 第六阶段：上线部署（交付阶段）
>
> * 一切就绪后，就是正式上线的时刻。工程师会将网站程序从测试服务器迁移到您购买的正式服务器上，并进行域名解析，让用户可以通过您的域名访问。上线后，通常还会进行一次最终测试，确保生产环境一切正常。
>
> 第七阶段：维护与运营（居住阶段）
>
> * 网站上线是真正的开始，而非结束。进入持续的维护与运营阶段，包括内容更新、安全补丁更新、数据备份、性能监控，以及根据数据反馈进行持续的优化迭代。

## 9.2 网页设计方法

<img src="https://gitee.com/featon/picture/raw/master/20261012144214665.png" alt="image-20230827083336291" style="zoom: 25%;" />

## 9.3 网页的布局

<img src="https://gitee.com/featon/picture/raw/master/20261012144219279.png" alt="image-20230826210943694" style="zoom:50%;" />

<img src="https://gitee.com/featon/picture/raw/master/20261012144222679.png" alt="image-20230826203033184" style="zoom: 33%;" />

<img src="https://gitee.com/featon/picture/raw/master/20261012144235889.png" alt="image-20230826203147174" style="zoom:33%;" />

网页设计及基本框架结构（**布局命名**）：匈牙利命名法！

> * [ ] Container
>   * “container“ 就是将页面中的所有元素包在一起的部分，这部分还可以命名为: “wrapper“, “wrap“, “page“
> * [ ] Header
>   * “header” 是网站页面的头部区域，一般来讲，它包含网站的logo和一些其他元素。这部分还可以命名为:“page-header” (或 pageHeader)。
>   * [ ] Logo
>     * 通常网站为体现其特色与内涵，涉及并制作一个LOGO图像放置在网站的左上角或其他醒目的位置。企业网站常常使用企业的标志或者注册商标。
>   * [ ] Banner
>     * “banner“是横幅，Banner的内容通常为网页中的广告。在网页布局中，大部分网页将Banner放置在与导航条相邻处，或者其他醒目的位置以吸引浏览者浏览。
> * [ ] Navbar
>   * “navbar“等同于横向的导航栏，是最典型的网页元素。这部分还可以命名为:“nav”, “navigation”, “nav-wrapper”。
> * [ ] Menu
>   * “Menu”区域包含一般的链接和菜单，这部分还可以命名为: “subNav “, “links“，“sidebar-main”。
> * [ ] Main
>   * “Main”是网站的主要区域，如果是博客的话它将包含的日志。这部分还可以命名为: “content“, “main-content” (或“mainContent”)。
> * [ ] Sidebar
>   * “Sidebar” 部分可以包含网站的次要内容，比如最近更新内容列表、关于网站的介绍或广告元素等…这部分还可以命名为: “subNav “, “side-panel“, “secondary-content“。
> * [ ] Footer
>   * “Footer”包含网站的一些附加信息，这部分还可以命名为: “copyright“。

## 9.4 Hello Wrold!

我的一个人网页（index.html）

> * [ ] 内容与结构（HTML）
> * [ ] 样式（CSS）
> * [ ] 交互（JavaScript）

Html源代码：[HTML 教程 | 菜鸟教程](https://www.runoob.com/html/html-tutorial.html)

![image-20261026160424071](https://gitee.com/featon/picture/raw/master/20261026160654568.png)

![img](https://gitee.com/featon/picture/raw/master/20261026160252781.jpeg)

> **<!DOCTYPE html>** 声明为 HTML5 文档
>
> **<html>** 元素是 HTML 页面的根元素
>
> **<head>** 元素包含了文档的元（meta）数据，如 **<meta charset="utf-8">** 定义网页编码格式为 **utf-8**。
>
> **<title>** 元素描述了文档的标题
>
> **<body>** 元素包含了可见的页面内容
>
> **<h1>** 元素定义一个大标题
>
> **<p>** 元素定义一个段落

### 9.4.1 HTML头部<head>

可以添加在头部区域的元素标签为: <title>, <style>, <meta>, <link>, <script>, <noscript> 和 <base>。

```html
<!-- <title> HTML文档的标题 -->
<title>文档标题</title>

<!-- <base> HTML文档基本的链接地址/链接目标 -->
<base href="http://www.XXX.com/images/" target="_blank">

<!-- <link> HTML文档与外部资源之间的关系 -->
<link rel="stylesheet" type="text/css" href="mystyle.css">
<link rel="shortcut icon" href="图片url">

<!-- <style> HTML文档的样式文件引用地址 -->
<style type="text/css">
body {
    background-color:yellow;
}
p {
    color:blue
}
</style>

<!-- <meta> 描述基本的元数据（关键是干啥用？） -->
<meta name="keywords" content="HTML, CSS, XML, XHTML, JavaScript">
<meta name="description" content="免费 Web & 编程 教程">
<meta name="author" content="featon">
<meta http-equiv="refresh" content="30">
<!-- 中文乱码 -->
<meta charset="utf-8" />
<meta charset="gbk" />

<!-- <script> 加载Javascript脚本文件 -->
<script>
	document.write("Hello World!")
</script>
<script src="../../js/jquery.js"></script>
```

### 9.4.2 HTML可见区<body>

HTML 文档由一系列 HTML 元素（Element）构成，是网页结构的基础。

![HTML 元素](https://gitee.com/featon/picture/raw/master/20261026170318777.png)

HTML 元素是从**开始标签（start tag）**到**结束标签（end tag）**之间的完整结构。

| 开始标签                                           | 元素内容           | 结束标签 |
| :------------------------------------------------- | :----------------- | :------- |
| <p>                                                | 这是一个段落       | </p>     |
| <a href="default.htm">                             | 这是一个链接       | </a>     |
| `<br>`（换行） `<img>`（图片） `<input>`（输入框） | 换行（**空元素**） | 无       |

空元素是指没有内容的元素。

```html
<!-- 小写标签 -->
<!-- HTML 标题 -->
<h1>这是一个标题</h1>
<h2>这是一个标题</h2>
<h3>这是一个标题</h3>

<!-- HTML 段落 -->
<p>这是一个段落。</p>
<p>这是另外一个段落。</p>

<!-- HTML 链接 -->
<a href="https://www.runoob.com">这是一个链接</a>

<!-- HTML 图像 -->
<img src="/images/logo.png" width="258" height="39" />
```

HTML 属性

- HTML 元素可以设置**属性**
- 属性可以在元素中添加**附加信息**
- 属性一般描述于**开始标签**
- 属性总是以名称/值对的形式出现，**比如：name="value"**

![HTML 属性](https://gitee.com/featon/picture/raw/master/20261026170440854.png)

### 9.4.3 常见的问题

* href 与 src 属性
  * **href** 表示超文本引用（hypertext reference），在 link和a 等元素上使用。src 表示来源地址，在 img、script、iframe 等元素上。
  * **src** 的内容，是页面必不可少的一部分，是引入。href 的内容，是与该页面有关联，是引用。区别就是，引入和引用。

```html
<link href="reset.css" rel=”stylesheet“/>
<script src="script.js"></script>
```

* 绝对路径与相对路径
  *  **./**：代表文件所在的目录（可以省略不写）如果写成image/background就相当于是在html文件下找image文件夹，当然是找不到的
  *  **../**：代表文件所在的父级目录
  *  **../../**：代表文件所在的父级目录的父级目录
  *  **/**：代表文件所在的根目录

```html
<img src="d:///f:/*.jpg" width="300" height="120"/>
<img src="*.jpg" width="300" height="120"/>
<img src="image/*.jpg/"width="300" height="120"/>
<img src="../image/*.jpg/"width="300" height="120"/>
<img src="http://static.runoob.com/images/runoob-logo.png" width="300" height="120"/>
```

* 注释

```html
<!-- 注释内容 -->
```

* target属性

|    取值    |             打开方式             |                典型场景                |
| :--------: | :------------------------------: | :------------------------------------: |
|   _self    |      当前页面打开（默认值）      |           站内导航、表单提交           |
|   _blank   |       新标签页/新窗口打开        |      外链、文档下载、保留当前页面      |
|  _parent   |         在父级框架中打开         |            iframe 嵌套页面             |
|    _top    |      跳出所有框架，顶层打开      |        防止被第三方 iframe 套壳        |
| 自定义名称 | 在指定名称的窗口 / iframe 中打开 | 多窗口应用，需匹配 <iframe name="xxx"> |

* HTML 颜色

HTML 是 24 位真彩色（RGB）？

三种颜色 红，绿，蓝的组合从0到255，一共有1600万种不同颜色。

256 x 256 x 256 = 2<sup>8</sup> x 2<sup>8</sup> x 2<sup>8</sup> =  2<sup>24</sup> 

|                        **颜色名**                         | 3位十六进制颜色值 | 6位十六进制颜色值 |       RGB        |
| :-------------------------------------------------------: | :---------------: | :---------------: | :--------------: |
| [Black](https://www.runoob.com/try/color.php?color=Black) |       #000        |      #000000      |    rgb(0,0,0)    |
|                                                           |       #F00        |      #FF0000      |   rgb(255,0,0)   |
|                                                           |       #0F0        |      #00FF00      |   rgb(0,255,0)   |
|                                                           |       #00F        |      #0000FF      |   rgb(0,0,255)   |
|                                                           |       #FF0        |      #FFFF00      |  rgb(255,255,0)  |
|                                                           |       #0FF        |      #00FFFF      |  rgb(0,255,255)  |
|                                                           |       #F0F        |      #FF00FF      |  rgb(255,0,255)  |
|                                                           |       #888        |      #888888      | rgb(136,136,136) |
| [White](https://www.runoob.com/try/color.php?color=White) |       #FFF        |      #FFFFFF      | rgb(255,255,255) |

* HTML 字符实体

| 显示结果 | 描述        | 实体名称          | 实体编号 |
| :------- | :---------- | :---------------- | :------- |
|          | 空格        | &nbsp;            | &#160;   |
| <        | 小于号      | &lt;              | &#60;    |
| >        | 大于号      | &gt;              | &#62;    |
| &        | 和号        | &amp;             | &#38;    |
| "        | 引号        | &quot;            | &#34;    |
| '        | 撇号        | &apos; (IE不支持) | &#39;    |
| ￠       | 分          | &cent;            | &#162;   |
| £        | 镑          | &pound;           | &#163;   |
| ¥        | 人民币/日元 | &yen;             | &#165;   |
| €        | 欧元        | &euro;            | &#8364;  |
| §        | 小节        | &sect;            | &#167;   |
| ©        | 版权        | &copy;            | &#169;   |
| ®        | 注册商标    | &reg;             | &#174;   |
| ™        | 商标        | &trade;           | &#8482;  |
| ×        | 乘号        | &times;           | &#215;   |
| ÷        | 除号        | &divide;          | &#247;   |

* head 与 header 的区别？
  * head 标签用于定义文档头部，它是所有头部元素的容器
  * header 语义化标签用于定义文档的页眉（介绍信息）

* HTML 语义化标签
  * `<header>`：页面或区块的头部，常放 Logo、导航 。
  * `<nav>`：专门包裹导航链接组，如主菜单、面包屑 。
  * `<main>`：页面主体内容，‌**一个页面只能出现一次**‌ 。
  * `<article>`：独立内容单元，如博客文章、新闻条目，可单独分发 。
  * `<section>`：有统一主题的内容区块，通常需搭配标题使用 。
  * `<aside>`：侧边辅助内容，如推荐阅读、广告，删除不影响主内容 。
  * `<footer>`：页面或区块底部，放版权、联系方式等 。‌‌‌

### 9.4.4 HTML 编辑器

*.html

> * [x] Notepad
> * [x] W3C在线
> * [x] DW / VSCode

## 9.5 个人主页

![img](https://gitee.com/featon/picture/raw/master/20261026172744121.jpeg)

从无到有的网页生产流程（**三步走**）：

> * [ ] 抽象（原型图、草稿）
> * [ ] 映射（效果图、设计稿）
> * [ ] 实现（**布局**）

三步走：

> * [ ] 第一步：抽象
>   * [ ] 头脑风暴（笔纸绘制草稿）
> * [ ] 第二步：映射
>   * [ ] 设计稿原型（PS / Figma / Lovart / Stitch）
>   * [ ] 观察、拆分设计稿（PS切图功能）
>   * [ ] 分离颜色：基本配色、超链接配色和导航链接配色
>   * [ ] 提取尺寸：网页分辨率是72ppi（像素/英寸），画布尺寸1920px*1080px，内容显示的区域为996px
>   * [ ] 分离背景图：CSS Sprites（精灵图）
>   * [ ] 分离图标及特殊边框
>   * [ ] 分离图片
> * [ ] 第三步：实现
>   * [ ] Table 布局
>   * [ ] Div + CSS 布局

**CSS禅意花园**

* [x] [CSS 禅意花园: CSS 设计之美 (csszengarden.com)](http://www.csszengarden.com/tr/zh-cn/)

<img src="https://gitee.com/featon/picture/raw/master/20261026112637305.png" alt="image-20230827100241336" style="zoom: 50%;" />

## 9.6 部署网站

从网页到网站（整体性原则）

> * [ ] 主页或首页：Index Page
> * [ ] 登录页：Login Page
> * [ ] 着陆页（引导页）：Landing Page
> * [ ] 导航链接：Navigation Page

本地部署：Nginx（IIS）

远程部署：Github / Cloudflare

## 9.7 作业三

从无到有，用传统方式制作 “个人主页”！

> * [x] 抽象（大脑）
> * [x] 映射（效果原型图）
> * [x] 实现（布局、代码）
> * [ ] 个人主页部署到 Github 上线（Assignment3）

后续仍有一个关键的问题：如何才能推广我的个人网站呢？

* SEO
* GEO
  * 解决 AI 幻觉
  * 虚假数据

## ★ ★ ★ 作业提交规范★ ★ ★

1. 目录命名：
   - 每人每次作业一个独立的文件目录。
   - 学号+姓名，注意顺序、中间无空格无  `+` 号，例如：20251060001张三。
2. 网页命名：
   - 不可以用中文或其他英文命名。
   - 首页：index.html
   - 一级页面：index01.html
   - 二级页面：index0101.html
3. 网站目录：
   - **images文件夹**：这个文件夹包含网站上使用的所有图片。
   - **styles文件夹**：这个文件夹包含用于设置内容样式的 CSS 代码（例如，设置文本和背景颜色）。
   - **scripts文件夹**：这个文件夹包含所有用于向网站添加交互功能的 JavaScript 代码（例如，点击时加载数据的按钮）。
4. CSS文件命名：layout.css
5. 注释：
   - html：<!-- 注释 -->
   - CSS：//和/* 注释 */
6. 语义化标签：
   - 页眉 <header>
   - 导航栏 <nav>
   - 主内容 <main>
   - 子内容 <article>、<section>、<aside>、<div>
   - 侧边栏 <aside>
   - 页脚 <footer>