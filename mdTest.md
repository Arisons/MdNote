####标题####
This is an H1
========
This is an H2
--------------
*此处的等号和中划线的数量不做限制*

#h1#
##h2##
###h3###
###3

*一次类推几个井号就是几号标题，可以不闭合（闭合只是为了美观）*   
“错误###”，*这种是错误的*

####区块标签####
#####每一句加一个区段#####
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
> 
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.
#####每一段加一个区段#####
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
id sem consectetuer libero luctus adipiscing.
#####嵌套区段#####
> This is the first level of quoting.
>
> > This is nested blockquote.
>
> Back to the first level.
#####引用的区段也可以使用Markdown语法#####
> ## 这是一个标题。
> 
> 1.   这是第一行列表项。
> 2.   这是第二行列表项。
> 
> 给出一些例子代码：
>    
>     return shell_exec("echo $input | $markdown_script");

#####列表#####
*   Red
*   Green
*   Blue

+   Red
+   Green
+   Blue

-   Red
-   Green
-   Blue

1. aa
2. bb
3. cc

*无序列表使用星号、加号或是减号作为列表标记，有序列表使用数字加英文句点*

######列表项目标记######
*	这是一个聊表项目标记
	* red
	* blue
*	这是另一个列表项目标记
	1. aa
	2. bb
#####列表项目可以包含多个段落#####
1.	每个项目下的段落都要缩进四个空格或一个制表符。
	这个是第二段。（中文下第二段就不会和第一段分开）
2.	每个项目下的段落都要缩进四个空格或一个制表符
3.	重要的事情说三遍

*   This is a list item with two paragraphs.

    This is the second paragraph in the list item. You're
only required to indent the first line. Lorem ipsum dolor
sit amet, consectetuer adipiscing elit.

*   Another item in the same list.

*每个项目下的段落都必须缩进 4 个空格或是 1 个制表符*

*   A list item with a blockquote:

    > This is a blockquote
    > inside a list item.

*如果在列表项目内放引用，那>需要缩进*

*   一列表项包含一个列表区块：

		<This is my code.>

*如果要放代码区块的话，该区块就需要缩进两次，也就是 8 个空格或是 2 个制表符*

#####代码区块####
要在 Markdown 中建立代码区块很简单，只要简单地缩进 4 个空格或是 1 个制表符就可以.例如，下面的输入

    tell application "Foo"
        beep
    end tell
    haha
    持续到没有缩进的哪一行或文件结尾		
*一个代码区块会一直持续到没有缩进的那一行（或是文件结尾）*
*在代码区块里面， & 、 < 和 > 会自动转成 HTML 实体*

例如：
	<div class="footer">&copy; 2004 Foo Corporation</div>
变成：
	<pre><code>&lt;div class="footer"&gt;
		&amp;copy; 2004 Foo Corporation
    &lt;/div&gt;</code></pre>

#####分隔线#####
* * *
***
****
---
-----

#####区段元素#####
要建立一个行内式的链接，只要在方块括号后面紧接着圆括号并插入网址链接即可，如果你还想要加上链接的 title 文字，只要在网址后面，用双引号把 title 文字包起来即可，例如：

这是一个行内的连接测试[我是连接](http://www.baidu.com "这是提示信息")

如果你是要链接到同样主机的资源，你可以使用相对路径：
See my [About](/about/) page for details.

链接内容定义的形式为：

方括号（前面可以选择性地加上至多三个空格来缩进），里面输入链接文字
接着一个冒号
接着一个以上的空格或制表符
接着链接的网址
选择性地接着 title 内容，可以用单引号、双引号或是括弧包着
下面这三种链接的定义都是相同：

This is [an example] [foo] reference-style link.

[foo]: http://example.com/  "Optional Title Here"
[foo]: http://example.com/  'Optional Title Here'
[foo]: http://example.com/  (Optional Title Here)

请注意：有一个已知的问题是 Markdown.pl 1.0.1 会忽略单引号包起来的链接 title。

#####强调#####
Markdown 使用星号（*）和底线（_）作为标记强调字词的符号

*single asterisks*

_single underscores_

**double asterisks**

__double underscores__

un **frigging** believable

\*this text is surrounded by literal asterisks\*

#####代码#####

如果要标记一小段行内代码，你可以用反引号把它包起来（`），例如：

Use the `printf()` function.

如果要在代码区段内插入反引号，你可以用多个反引号来开启和结束代码区段：

``There is a literal backtick (`) here.``

代码区段的起始和结束端都可以放入一个空白，起始端后面一个，结束端前面一个，这样你就可以在区段的一开始就插入反引号：

A single backtick in a code span: `` ` ``

A backtick-delimited string in a code span: `` `foo` ``
是这个样子的吗？我也试试 `` `我是代码这你能信` ``

#####图片#####
行内式的图片语法看起来像是：

![Alt text](http://www.16sucai.com/uploadfile/2013/0616/20130616030823418.png)

![Alt text](http://www.16sucai.com/uploadfile/2013/0616/20130616030823418.png "路飞")
详细叙述如下：

一个惊叹号 !
接着一个方括号，里面放上图片的替代文字
接着一个普通括号，里面放上图片的网址，最后还可以用引号包住并加上 选择性的 'title' 文字。
参考式的图片语法则长得像这样：

![Alt text][lf]
「id」是图片参考的名称，图片参考的定义方式则和连结参考一样：

[lf]: http://www.16sucai.com/uploadfile/2013/0616/20130616030823418.png  "蒙奇迪路飞"
到目前为止， Markdown 还没有办法指定图片的宽高，如果你需要的话，你可以使用普通的 <img> 标签。

#####自动连接#####
<http://example.com>

<983332827@qq.com>



