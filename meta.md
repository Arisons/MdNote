meta标签属性详解
--------------------
#####概述#####
meta是html语言head部分的一个辅助标签。也许你认为这些代码可有可无。其实如果你能够用好meta标签，会给你代理意想不到的效果，meta标签的作用：搜索引擎优化（SEO），定义页面使用语言，自动刷新并指向新的页面，实现网页转换时的动态效果，控制页面缓冲，网页定级评价，控制网页像是的窗口等！

meta标签的组成：meta标签共有两个属性，他们分别是http-equiv属性和name属性，不同的属性又有不同的参数值，这些不同的参数就实现了不同的网页功能。

>name属性
>name属性主要用于描述网页，与之对应的属性值为content，content中的内容主要是便于引擎机器人查找信息和分类信息用的。
>meta标签的name属性语法格式：

	<meta name="参数" content="具体的参数值">
#####其中name属性主要有一下几种参数：#####
>
*	keywords（关键词）
*	说明：keywords用来告诉搜索引擎你网页的关键字是什么。
*	举例：

	<meta name="keywords" content="science,education,culture,politics,ecnomics,relationships,entertainment,human">
>
*	description（网站内容描述）
*	说明：description用来告诉搜索引擎你的网站主要内容。
*	举例：

	<meta name="description" content="this pages is about the meaning of science,education,culture">
>
*	robots（机器人向导）
*	说明：robots用来告诉搜索机器人那些页面需要索引，那些页面不需要索引
*	content的参数有 all/none/index/noindex/follow/nofollow。默认是all
*	举例：

	<meta name="robots" content="none">
>
*	author（作者）
*	说明：标注网页的作者
*	举例：

	<meta name="author" content="root,root@xxxx.com">
#####http-equiv属性#####
>http-equiv顾名思义，相当于http的文件头，它可以向浏览器回传一些有用的信息，以帮助正确和精确地显示网页内容，与之对应的属性值为content，content中的内容其实就是各个参数的变量值。
>
>meta标签的http-equiv属性语法格式：

	<meta http-equiv="参数" content="参数变量值">
>#####其中http-equiv属性主要有一下几种参数 
>expires（期限）
>
*	说明：可以用于设定网页的到期时间。一旦网页过期，必须到服务器上重新传输。
*	用法

	<meta http-equiv="expires" content="Fri,12Jan200112:18:18GMT">
>Pragma(cache模式)
>
*	注意：这样设定访问者无法脱机浏览
*	说明：禁止浏览器从本地计算机的缓存中访问页面内容。
*	用法：

	<meta http-equiv="Pragma" content="no-cache">
>Refresh（刷新）
>
*	说明：自动刷新并指向新页面。
*	注意：其中的2是指停留2秒后自动刷新到url网址
*	用法：

	<meta http-equiv="Refresh" content="2;URL=http://www.baidu.com">
	//注意后面的分号
>Set-Cookie(cookie设定)
>
*	说明：如果网页过期，那么存盘的cookie将被删除
*	注意：必须使用GMT的时间格式
*	用法：
	
	<meta http-equiv="Set-Cookie" content="cookievalue=xxx;expires=Friday,12-Jan-200118:18:18GMT;path=/">
>Window