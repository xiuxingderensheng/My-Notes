[TOC]
#第二章 初始 HTML5
##2.3  “Hello World” 旅程
###2.3.4  HTML5 “严格” 风格的 “Hello World!”
```
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>Hello World</title>
    </head>
    <body>
        <p>Hello World</p>
    </body>
</html>
```

##2.4  让 HTML5 得到跨浏览器支持
```
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>Styling Unknown Elements - 4</title>
        <!--[if lt IE9]>
            <script src="http://html5shiv.googlecode.com/svn/trunk/html5.js"></script>
        <![endif]-->
        <style>
            time{
                font-style: italic;
            }
        </style>
    </head>
    <body>
        <p>Miss Baker made her historic journey on <time datetime="1959-05-28">May 28, 1958</time>.</p>
    </body>
</html>
```

##2.5  HTML5 样板页面
```
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>Styling Unknown Elements - 4</title>
        <!--[if lt IE9]>
            <script src="http://html5shiv.googlecode.com/svn/trunk/html5.js"></script>
        <![endif]-->
        <style>
            article, aside, details, figcaption, figure, footer, header, hgroup, menu, nav, section{
                display: block;
            }
        </style>
    </head>
    <body>
        <p>Insert your content here.</p>
    </body>
</html>
```

###2.5.1  不再有 type 属性

#第三章  新的结构化元素
##3.2  新语义化开端
用于页面片段的新元素，称为结构化元素，可以代替以前的 class 和 id 。
&lt;section&gt;
&lt;article>&gt;
&lt;header>&gt;
&lt;footer>&gt;
&lt;hgroup>&gt;
&lt;nav>&gt;
&lt;aside>&gt;

##3.3  结构化构建块&lt;div&gt;、&lt;section&gt;和article&gt;
* **&lt;div&gt;：**一般性的容器，无附加语义。
* **&lt;section&gt;：**文档或应用程序的一般性小节（“节”、“片段”、“部分”）。
* **&lt;article&gt;：**文档或网站的一个独立的小节。

###3.3.2  选用哪一个
（1）被封装的内容在馈送阅读器中会有完整意义吗？是，则用 article   
（2）被封装的内容相关吗？如果是，则用 section 。  
（3）如果没有语义关系，则用 div 。

###3.3.3  使用这些元素的基本结构
见 test3_3.html 。

##3.4  &lt;header&gt;、&lt;hgroup&gt;、&lt;h1&gt;~&lt;h6&gt;以及&lt;footer&gt;
**注意**  
分节元素包括section、article、aside以及nav，此外还有blockquote、body、details、fieldset、figure和td等。*

* **&lt;header&gt;：**用于分节元素的内容介绍和导航。不能再包含footer或header。
* **&lt;footer&gt;：**用于表现内容的附加信息，如作者、版权数据等。一般在内容的底部。不能再包含footer或header。
* **&lt;hgroup&gt;：**是header的一种特殊形式，只能包含h1~h6元素。
* **&lt;h1&gt;~&lt;h6&gt;：**

具体例子见test3_4.html。

##3.5  HTML5的大纲算法
大纲是通过内容分节元素的标题形成的，他们定义了页面有关内容的块结构。
每个内容分节元素的第一个&lt;h1&gt;~&lt;h6&gt;会作为大纲中该小节的标题，而其后续的标题会形成大纲中一个隐式的封装小节。

##3.7  更多的结构化元素：&lt;nav&gt;、&lt;aside&gt;、&lt;figure&gt;以及&lt;figcaption&gt;

* **&lt;nav&gt;：**导航链接小节。
* **&lt;adide&gt;：**页面的一个小节，由与周边内容略微相关但又单独分开的内容组成。
* **&lt;figure&gt;：**对理解至关重要，但可以在文档流中迁移，而不影响文档的含义。

具体使用见test3_7.html



## 3.8  综合到一起

见test3_8.html。





## 3.9  HTML5与可访问性

**1. &lt;img&gt; 的 alt 属性**



### 3.9.3  HTML5的其他可访问性问题

&lt;video&gt; 与 &lt;audio&gt; 等标签。





# 第四章  更丰富的内容标记方法

注意元素的的语义含义。



## 4.1  以前的表现式元素与助手

HTML4的一些元素的表现式定义是以它们的屏幕外观为基础的，这无助于使用辅助技术的用户，如有视觉障碍的人。HTML5对此进行了修正。

* &lt;i&gt;原来是斜体，现在用于“另一种声音”。形式的文本，例如外来词、技术术语以及分类名称等。
* &lt;b&gt;原来是粗体，现在用于修饰仅仅是出于使用目的地引人注意的文本。
* &lt;em&gt;原来是强调，现在是重音强调。
* &lt;strong&gt;原来是着重强调，现在用于表现十分重要的内容。而在希望用斜体而不带隐含的强调时，使用&lt;i&gt;。&lt;em&gt;中嵌套&lt;em&gt;表示等级。
* &lt;small&gt;用于表示旁注，如小字号印刷体，主要用于表示一些不重要的。
* &lt;hr&gt;原来是一条水平线，现在用作 “段落级的主题分隔” 。
* &lt;s&gt;原来是删除线，现在用于表示 “不再相关或不准确” 的内容。
* &lt;u&gt;原来是下划线文本，现在表示一段发音不清、虽已显示渲染但并非正文注释的文本。


##4.2  带有&lt;a&gt;元素的块级链接

在&lt;a&gt;标签中先嵌套一层&lt;div&gt;标签可以在一定程度上避免样式误差，尤其是在Firefox浏览器中。

##4.3  其他 HTML4 略有变化的元素

```
<!-- type: 1/a/A/i/I;attr: "start" and "value" and "reversed" -->
<ol type="a" reversed>
    <li value="5">5</li>
    <li>6</li>
    <li>7</li>
    <li>8</li>
</ol>

<!-- dl元素用于表现关联列表，由零个或多个 “键/值对” 组成。 -->
<dl>
    <dt><strong>处理器</strong></dt>
    <dd>高通骁龙835低配版</dd>
    <dd>高通骁龙835标准版</dd>
    <dd>高通骁龙835高配版</dd>
    <dt><strong>屏幕</strong></dt>
    <dd>3D曲面玻璃</dd>
    <dt><strong>分辨率</strong></dt>
    <dd>2K屏</dd>
</dl>

<blockquote>
    <p>
        <!-- mark元素既不是强调也不影响重要性，用于表现作为参考的文本。 -->
        <strong>Dogs are the best!</strong>They are <em>obviously</em> much cooler than monkeys, even if <mark>the 
        first animal in space was a monkey</mark>.
    </p>
</blockquote>

<!-- datetime属性使得时间有了机器可读性。当然，也可以用data-*代替。 -->
今天是<time datetime="2016-12-21">公元2016年12月21日</time>。PM2.5为<data value="132">132</data>，轻度污染，
比昨天的<data value="482">482</data>要好！

```



#第 5 章  富媒体

##5.2  HTML5 的视频之路
没有一种单一的容器和编解码器组合能够在所有HTML5浏览器中工作。所以需要对视频进行多次编码。
还可以增加Flash备用文案，用于不支持VP8的HTML5浏览器。

```
<h2>All Three (WebM, MP4, OGG) by HTML5</h2>
    <video poster="poster.jpg" controls="controls" width="720" height="405">
        <!-- video的src去掉，source的type必须要有，保留download链接，三个source的顺序也很重要。 -->
        <source src="gordoinspace.mp4" type="video/mp4">
        <source src="gordoinspace.webm" type="video/vp8">
        <source src="gordoinspace.ogv" type="video/ogg">
        Download <a href="gordoinspace.webm">Gordo in Space</a> the movie.
    </video>

    <h2>All Three (WebM, MP4, OGG) by HTML5 and Flash</h2>
    <video poster="assets/poster.jpg" controls width="720" height="405">
        <source src="assets/big_buck_bunny.mp4" type="video/mp4" />
        <source src="assets/big_buck_bunny.webm" type="video/vp8" />
        <source src="assets/big_buck_bunny.ogv" type="video/ogg" />
        <object id="player" classid="clsid:D27CDB6E-AE6D-11cf-96B8-444553540000" name="player" width="720" height="429"> 
            <param name="movie" value="player.swf" /> 
            <param name="allowfullscreen" value="true" /> 
            <param name="allowscriptaccess" value="always" /> 
            <param name="flashvars" value="file=assets/big_buck_bunny.mp4&image=assets/poster.jpg" /> 
            <embed 
                type="application/x-shockwave-flash"
                id="player2"
                name="player2"
                src="player.swf" 
                width="720" 
                height="429"
                allowscriptaccess="always" 
                allowfullscreen="true"
                flashvars="file=file=assets/big_buck_bunny.mp4&image=assets/poster.jpg" 
            />
            <!-- 图片用于提醒尚未安装Flash的用户 -->
            <img src="assets/poster.jpg" title="No video playback capabilities, please download the video below">
            <p>Your browser doesn't support video, please <a href="assets/big_buck_bunny.webm">download it</a>.</p>
        </object> 
    </video>

    <h2>添加字幕支持，使用track元素</h2>
    <video src="gordoinspace.webm" width="720" height="405" poster="poster.jpg" controls="controls">
        <!-- vtt是一种 WebVTT文件，用于标记外部文本轨道。 -->
        <track kind="subtitles" src="gordo_subtitles_en.vtt" srclang="en" label="English" />
        <track kind="subtitles" src="gordo_subtitles_de.vtt" srclang="de" label="Deutsch" />
        <track kind="subtitles" src="gordo_subtitles_fr.vtt" srclang="fr" label="Francais" />
    </video>
```

##5.3  音频
audio 和 video 很相似。

###5.3.1  音频解码器
* Vorbis
* MP3
* AAC
* WAV
* MP4

```
<audio controls="">
    <source src="gordo_interview.mp3" type="audio/mp3">
    <source src="gordo_interview.aac" type="audio/aac">
    <source src="gordo_interview.ogg" type="audio/ogg">
    Download <a href="gordo_interview.ogg">Gordo interview</a>.
</audio>
```

##5.4  Canvas

##5.5  SVG
Scalable Vector Graphics(SVG，可缩放矢量图)。SVG 并不是 HTML5 的一部分，但 HTML5 可以嵌入内联的 SVG 。

SVG 比较适用于图表和分辨率独立的图形、动画交互的用户界面或矢量图像编辑。canvas 适合于游戏、位图图像处理、光栅图形以及图像分析。

```
<svg xmlns="http://www.w3.org/2000/svg" width="400px" height="400px" version="1.1">
    <defs>
        <linearGradient id="TestGradient" gradientTransform="rotate(45)">
            <stop offset="0%" stop-color="#6c88ba" />
            <stop offset="90%" stop-color="#677794" />
            <stop offset="100%" stop-color="#6e747f" />
        </linearGradient>
    </defs>

    <circle fill="url(#TestGradient)" stroke="black" cx="150" cy="150" r="150" />
</svg>
```


#第 6 章 为 Web 应用程序铺平道路

HTML5表单的一些新元素和新属性。实现了优雅降级和良好的交互性，也为表单验证提供了原生的支持，提高了开发效率。另外，HTML5的API也为Web应用程序铺平了道路。


#第 7 章  CSS3简介

##7.7  级联/特性和继承

###7.7.1  级联

* （1）来自浏览器的用户代理样式
* （2）用户样式
* （3）作者样式
* （4）标记为 !important 的作者样式
* （5）标记为 !important 的用户样式

###7.7.2  计算特性

有4个级别：  
* a = 内敛样式(1000)
* b = ID选择器的总数(100)
* c = 类和属性选择器以及伪类的数量(10)
* d = 类型选择器和伪元素的数量(1)

例如：  
* style="color:red;": (a,b,c,d) = (1,0,0,0) 1000
* #comments #respond{...}: (a,b,c,d) = (0,2,0,0) 200
* #respond input[type="checkbox"]{...}: (a,b,c,d) = (0,1,1,1) 111
* body#blog article.hentry p:first-child{...}: (a,b,c,d) = (0,1,2,3) 123
* body#blog article[role="main"] p:first-child{...}: ~ = (0,1,2,3) 123

###7.7.3  CSS继承

例如：  
article, section, h1, h2, h3, ol, ul, dl, p {font-family: georgia, serif;}  
or  
body {font-family: georgia, serif;}  
font-family 属性由主体的子元素继承，直到另一种样式将其重写为止。  
***虽然不是自动继承所有CSS属性，但是可以通过 inherit 强制继承。inherit 在低于 IE8 的版本上不能运行，除了 direction 和 visibility 属性外。***

##7.8  CSS组织和维护

###7.8.1  CSS协定

**1. 写成多行**  
```
h1 {
    font-family: Georgia;
    color: green;
    line-height: 1.3;
}
/* instead of below */
h1 {font-family: Georgia;color: green;line-height: 1.3;}
```

**2. 排列声明**  
单个规则集里可以按字母顺序/类型/相关性排列，甚至可以组合起来使用。  
例如下面就是按字母顺序排序的：  
```
header {
    background: #f8f8f8 url(img/bg.png);
    border-bottom: 1px solid #ccc;
    color: #333;
    font-family: Georgia;
    font-size: 16px;
    font-weight: normal;
    height: 60px;
    left: 0;
    line-height: 1.5;
    margin: 0 auto;
    padding: 5px 20px;
    position: fixed;
    top: 0;
    z-index: 2;
}
```
按照类型分组排列：  
1. Position
2. Display and box model
3. Font and typography
4. Color
5. Background and borders

```
header {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 2;
    height: 60px;
    margin: 0 auto;
    padding: 5px 20px;
    font-family: Georgia;
    font-size: 16px;
    font-weight: normal;
    line-height: 1.5;
    color: #333;
    background: #f8f8f8 url(ima/bg.png);
    border-bottom: 1px solid #ccc;
}
```
**3. 规则集可以按照骨架来排序**  
当然，也可以按照自己的偏好来排序。

**4. 命名约定**  
命名可以是描述性的和语义的，它们应该描述内容而不是表示。例如：  
```
.bigLeftCol {...}
.littleRightCol {...}
/* 下面的示例更精确地描述了内容而不是表示 */
.primary-content {...}
.secondary-content {...}
```
当然，CamelCase 命名法也有人用，但不是很推荐。

###7.8.2  注释最佳实践
```
/*-----------------------------------------------------------
[Master sheet]

Project:          Animals in Space
URL:              http://thewebevolved.com
Version:          1.1
Creator:          Rich Clark
Last changed:     01/02/12
Last Updated:     Oli Studholme
Primary use:      Demo site for book
-----------------------------------------------------------*/

/*-----------------------------------------------------------
Table of contents

1. Reset
2. Typography
3. Basic layout
4. Widgets
5. Media items
6. Forms
7. Media queries
8. IE specific styles
-----------------------------------------------------------*/

/*-----------------------------------------------------------
ξWidgets
-----------------------------------------------------------*/

/*-----------------------------------------------------------
Color reference sheet

Background:      #f8f8f8 (off white)
Body text:       #444 (dark grey)
Headings:        #888 (light grey)
:link            #0090D2 (blue)
:hover,
:active,
:focus:          #0063A6 (dark blue)
-----------------------------------------------------------*/

/*-----------------------------------------------------------
Typography reference sheet

Body copy:         1.2em/1.6em Goergia serif;
Headers:           2.7em/1.3em Helvetica, Arial, "Lucida Sans Unicode",
... ...
-----------------------------------------------------------*/
```

###7.8.3  CSS 重置和 normalize.css

**1. 使用重置**  

不建议下面的写法：  

```
* {
    margin: 0;
    padding: 0;
}
```
会使得站点变慢。而且有些元素的填充和页边距是不需要删除的。  
更常见的方法是使用自定义的重置样式表。  
*注意：谨慎使用重置，避免过度影响项目！*  

**2. 使用normalize.css**  
s
与重置相比，normalize.css 的目的是让浏览器显示的元素更符合现代浏览器的标准。

###7.8.5  可维护的CSS

收到设计稿的时候，可以问一些这样的问题：  

* 站点是定宽的，还是可响应的？
* 如果容器中没有图像，该怎么办？
* 如果在那里输入了过多的文本，该怎么办？
* 如果这个标题换行了，该怎么办？

**1. 创建模式基本件或组件库**  

最重要的一点是，组件必须是松耦合的，各个组件之间不能有依赖关系，组件也不应依赖于所处的环境，表现始终如一。

**2. 可行的可维护的CSS**  

* 考虑组件，而不是页面
* 考虑事物的类型，而不是单个事物
* 使用类，而不是ID
* 创建可组合的类
* 使用派生选择器，避免多余的类
* 使选择器尽可能短
* 按特性松散地整理 CSS 规则
* 使用百分数，而不是内部的布局尺寸


##7.9  浏览器支持/厂商前缀/填充物和渐进增强

**渐进增强**  

渐进增强应该是一种附加的功能，仅仅是为了使用户体验更好。换句话说，就算没有渐进增强的功能，也不应该影响网站的实用性。  

**厂商前缀**  

需要厂商前缀的特性最后有可能会被剔除，所以不要把这些特性用到网站的核心功能上。

* 对于支持每个前缀的所有浏览器，都包含一个带前缀的代码行。
* 另一个浏览器添加带前缀的支持时，就添加它。
* 规范改变时，就更新代码。
* 不再需要带前缀的声明时，就删除它。


###7.10  功能检测和填充物

**功能检测**  

Modernizr

**填充物**  

IE专用的填充物：  

* Selectivizr
* CSS3 PIE


#第 8 章  使用 CSS 选择器使标记尽量简短

##8.1  选择器概述

CSS1 引入了以下选择器：  

* 类型 （例如，p {...}, blockquote {...}）
* 后继组合器 （例如，p blockquote {...}）
* ID
* 类
* 链接伪类 （例如，a:link {...} 或 a:visited {...}）
* 用户动作伪类 （例如，a:active {...}）
* :first-line 伪元素（例如，p:first-line {...}）
* :first-letter 伪元素（例如，p:first-letter{...}）

CSS2.1 添加了另外11个选择器

* 通用（例如，* {...}）
* 用户动作伪类（例如，a:hover {...} 和 a:focus {...}）
* :lang() 伪类（例如，article: lang(fr) {...}）
* 结构伪类（例如，p:first-child {...}）
* :before 和 :after 伪类 （例如，blockquote:before {...} 或 blockquote:after {...}）
* 子组合器（例如，h2 > p {...}）
* 同级组合器（h2 + p {...}）
* 特性选择器（例如，input[required] {...}）
* 特性选择器；精确等于（例如，input[type="checkbox"] {...}）
* 子串特性选择器；一等于字符串（例如，input[class~="long-field"] {...}）
* 子串特性选择器；字符串台的开头用连字符分隔（例如，input[lang|="en"] {...}）

CSS3 中添加的一些选择器：  

* 一般同级组合器（例如，h1~pre {...}）
* 子串特性选择器；字符串以子串开头（例如，a[href^="http://"] {...}）
* 子串特性选择器；字符串以子串结尾（例如，a[href$=".pdf"] {...}）
* 子串特性选择器；字符串包含子串（例如，a[href*="twitter"] {...}）
* :target 伪类（例如，section: target {...}）
* 结构伪类；:nth-child （例如，tr: nth-child(even) td {...}）
* 结构伪类；:nth-last-child （例如，tr: nth-last-child(-n+5) td {...}）
* 结构伪类；:last-child （例如，ul li: last-child {...}）
* 结构伪类；:only-child （例如，ul li: only-child {...}）
* 结构伪类；:first-of-type （例如，p: first-of-type {...}）
* 结构伪类；:last-of-type （例如，p: last-of-type {...}）
* 结构伪类；:nth-of-type （例如，li: nth-of-type(3n) {...}）
* 结构伪类；:nth-last-of-type （例如，li: nth-last-of-type(1) {...}）
* 结构伪类；:only-of-type （例如，article img:only-of-type {...}）
* 结构伪类；:empty （例如，aside:empty {...}）
* 结构伪类；:root （例如，:root {...}）
* UI 元素状态伪类；:disabled 和 :enabled （例如，input:disabled {...}）
* UI 元素状态伪类；:checked （例如，input[type="checkbox"]:checked {...}）
* 否定伪类；:not （例如，abbr:not([title]) {...}）


##8.2  CSS3 选择器

###8.2.1  组合器

子组合器只会选择父元素中的直接子元素。即只选孩子不选孙子。而后继选择器会选择在父元素内部的孩子以及孙子等。

```
article > p {
    font-size: 125%;
}
```

邻近同级选择器会选择文档树中彼此相邻，且有相同父元素的元素。

```
h2 + p {
    font-weight: bold;
}
```

下面的代码说明了哪个选择器会选择哪个段落：

```
<article>
    <h1>Article title</h1>
    <p>...</p><!-- Child combinator targets this paragraph -->
    <section>
        <h2>Section title</h2>
        <p>...</p><!-- Adjacent sibling combinator targets this paragraph -->
        <p>...</p>
    </section>
    <p>...</p><!-- Child combinator targets this paragraph -->
</article>
```

CSS3 中还加入了一般同级选择器，第二个选择器不需要紧跟在第一个后面。

```
h3 ~ ul {
    list-style-type: binary;
}
```

下面是综合三种组合选择器的例子：

```
<article>
    <h1>Article title</h1>
    <p>...</p><!-- Child combinator targets this paragraph -->
    <section>
        <h2>Section title</h2>
        <p>...</p><!-- Adjacent sibling combinator targets this paragraph -->
        <p>...</p>
        <ul>
            <li>...</li>
            <li>...</li>
            <li>...</li>
        </ul>
        <section>
            <h3>Section Title</h3>
            <p>...</p>
            <p>...</p>
            <ul><!-- General sibling combinator targets this list -->
                <li>...</li>
                <li>...</li>
                <li>...</li>
            </ul>
        </section>
    </section>
    <p>...</p><!-- Child combinator targets this paragraph -->
</article>
```

###8.2.2  特性和子串选择器

###8.2.3  UI元素状态伪类
s
例如：  

* input: disabled
* input[type="checkbox"]:checked+label
* input[type="text"]:enabled, input[type="password"]:enabled


###8.2.4  Target 伪类

当 a 标签的 href 属性指向某元素的 ID 时，单击链接后就可以通过 :target 找到 ID 所对应的元素。  
具体实例见 test8_2_4.html 和 test8_2_4'.html 。


###8.2.5  结构伪类

**1. :first-child**  

选择给定元素的第一个子元素。

**2. :last-child**  

选择给定元素的最后一个子元素。

**3. :nth-child**

选择给定父元素的一个或多个特定的子元素。根据所给的参数而定。它可以将数字（整数）/关键字（odd 或 even）或计算式（表达式）作为参数。  
例如：  

* :nth-child：偶数
* :nth-child(2n)：每隔一行指定样式，0，4，6，...
* :nth-child(4n)：每隔三行指定样式
* :nth-child(4n+2)：从第二行开始，每隔三行指定样式
* :nth-child(-n+5)：-表示从后往前数。选出前五个元素

**4. :nth-last-child**  

与 :nth-child 类似，只不过是从后往前计数。

例如：  

* nth-last-child(-n+5)：选出后5个元素。

**5. :only-child**  

选出父元素的唯一子元素。  
例如：  

* ul li:only-child {...}

**6. :first-of-type**  

“类型” 伪类的工作方式与 “子元素” 选择器相同，其关键区别是 “类型” 伪类只选择与应用了选择器的元素类型相同的元素。即 “类型” 伪类是按标签类型来选择的，“子元素” 选择器是根据父子关系来选择的。  

**7. :last-of-type**  

例如s：  

* nav li:last-of-type {...}：给 nav 元素中的多个 li 元素中的最后一个添加样式

**8. :nth-of-type**  

**9. :nth-last-of-type**  

**10. :only-of-type**  

**11. :empty**  

:empty 表示没有内容的元素。  

**12. :root**

选中 html 元素。


###8.2.6  伪元素

伪元素用 “::” 以区分伪类。

**1. ::before 和 ::after**  

::before 和 ::after 伪元素用于在元素的内容（或另一个伪元素）之前或之后生成内容。因此，对于有空内容模式的元素，例如&lt;img&gt;和&lt;input&gt;，不能使用 ::before 和 ::after。  
伪元素生成的内容有 content 属性提供，它可以带有一下一个或多个值：  

* **字符串：**文本内容
* **URL：**外部资源的URL
* **计数器：**自动生成元素的编号
* **特性值：**带有指定特性值的字符串
* **左右引号：**值用引号属性中的字符串代替
* **无左右引号：**没有引入内容，但增加了嵌套层数

```
<!doctype html>
<html>
<head>
<meta charset="UTF-8" />
<title>test</title>
<style type="text/css">
a#one::after {
	content: "\2191";
}
p:nth-of-type(2n) {
	position: relative;
}s
a[href^="http://"]:hover::after, a[href^="http://"]:focus::after {
	content: attr(href) ;
	position: absolute;
	width: auto;
	bottom: -22px;
	left: 0;
	padding: 0 5px;
	color: #444;
}
p:last-of-type {
	position: relative;
}
a#three:hover::after, a#three:focus::after {
	content: "External Link" attr(href);
	position: absolute;
	width: auto;
	bottom: -22px;
	left: 0;
	padding: 0 5px;
	color: #444;
}
</style>
<head>
<p><a href="#" id="one">Back to top</a></p>
<p><a href="http://www.baidu.com" id="two">baidu.com</a></p>
<p><a href="www.google.com" id="three">google.com</a></p>
</html>
```

**2. 进一步研究伪元素**  

伪元素的潜能很大，应用范围也很广，包括页面翻卷/自动给各部分或各章编号等。甚至可以在打印的样式表中包含URL。  
下面是两个可以深入了解伪元素的链接：  

* [1](www.w3.org/TR/2009/CR-CSS2-20090908/generate.html)
* [2](www.w3.org/TR/css3-content/)

###8.2.7  否定伪类

选择不匹配选择器参数的元素。  

```
input:not([type="submit"]) {
    width: 250px;
    border: 1px dotted red;
}
```


##8.3  浏览器支持

CSS3 选择器在IE9+/Firefox 3.5+/Chrome 4+/Safari 4+ 和 Opera 10+ 上获得完全支持。但IE6/IE7/IE8 不支持CSS3 选择器（IE7/IE8 支持一般同级组合器/:first-child 和所有特性选择器）。可以用jQuery解决。  


#第 9 章  每种情形的布局










