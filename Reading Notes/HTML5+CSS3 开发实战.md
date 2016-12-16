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
（1）被封装的内容在馈送阅读器中会有完整意义吗？是，则用 article 。
（2）被封装的内容相关吗？如果是，则用 section 。
（3）如果没有语义关系，则用 div 。

###3.3.3  使用这些元素的基本结构
见 test3_3.html 。

##3.4  <header>、<hgroup>、<h1>~<h6>以及<footer>
**注意**
*分节元素包括section、article、aside以及nav，此外还有blockquote、body、details、fieldset、figure和td等。*

* **&lt;header&gt;：**用于分节元素的内容介绍和导航。不能再包含footer或header。
* **&lt;footer&gt;：**用于表现内容的附加信息，如作者、版权数据等。一般在内容的底部。不能再包含footer或header。
* **&lt;hgroup&gt;：**是header的一种特殊形式，只能包含h1~h6元素。
* **&lt;h1&gt;~&lt;h6&gt;：**

具体例子见test3_4.html。

##3.5  HTML5的大纲算法
大纲是通过内容分节元素的标题形成的，他们定义了页面有关内容的块结构。
每个内容分节元素的第一个&lt;h1&gt;~&lt;h6&gt;会作为大纲中该小节的标题，而其后续的标题会形成大纲中一个隐式的封装小节。

##3.7  更多的结构化元素：<nav>、<aside>、<figure>以及<figcaption>

* **<nav>：**导航链接小节。
* **<adide>：**页面的一个小节，由与周边内容略微相关但又单独分开的内容组成。
* **<figure>：**对理解至关重要，但可以在文档流中迁移，而不影响文档的含义。

具体使用见test3_7.html



