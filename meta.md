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
>#####Window-target（显示窗口设定）#####
*   说明：轻质页面在当前窗口以独立页面显示。
*   注意：这个属性是用来防止别人在框架里面调用你的页面。
*   Content选项：_blank _top _self _parent
*   用法：


    <meta http-equiv="Window-target" Content="_top">
>#####Pics-label（网页RSAC等级评定）#####
*   说明：在IE的Internet选项有意向内容设置，可以防止浏览器一些限制的网站，而网站的限制级别就是通过该参数来设置的。
*   注意：不要将级别设置的太高。RSAC的评估系统提供了一种用来评价Web站点内容的标准。用户可以设置Microsoft Internet Explorer（IE3.0以上）来排除包含有色情和暴力内容的站点。上面这个例子中的HTML取自Microsoft的主页。代码中的（n 0 s 0 v 0 l 0）表示该站点不包含不健康内容。级别的评定是由RSAC，即美国娱乐委员会的评级机构评定的，如果你想进一步了解RSAC评估系统的等级内容，或者你需要评价自己的网站，可以访问RSAC的站点：http://www.rsac.org/.
*   用法：

    <META http-equiv="Pics-label" Contect="(PICS－1.1'http://www.rsac.org/ratingsv01.html'I gen comment 'RSACi North America Sever' by 'inet@microsoft.com'for 'http://www.microsoft.com' on '1997.06.30T14:21－0500' r(n0 s0 v0 l0))">

>#####Page-Enter、Page-Exit (进入与退出)#####
*   说明：这个是页面被载入和调出时的一些特效。
*   注意：blendTrans是动态滤镜的一种，产生渐隐效果。另一种动态滤镜RevealTrans也可以用于页面进入与退出效果:
*   用法：


    <Meta http-equiv="Page-Enter" Content="blendTrans(Duration=0.5)">
    <Meta http-equiv="Page-Exit" Content="blendTrans(Duration=0.5)">
    <Meta http-equiv="Page-Enter" Content="revealTrans(duration=x, transition=y)">
    <Meta http-equiv="Page-Exit" Content="revealTrans(duration=x, transition=y)">
    //Duration　　表示滤镜特效的持续时间(单位：秒)
    //Transition　滤镜类型。表示使用哪种特效，取值为0-23。
    //0 矩形缩小
    //1 矩形扩大
    //2 圆形缩小
    //3 圆形扩大
    //4 下到上刷新
    //5 上到下刷新
    //6 左到右刷新
    //7 右到左刷新
    //8 竖百叶窗
    //9 横百叶窗
    //10 错位横百叶窗
    //11 错位竖百叶窗
    //12 点扩散
    //13 左右到中间刷新
    //14 中间到左右刷新
    //15 中间到上下
    //16 上下到中间
    //17 右下到左上
    //18 右上到左下
    //19 左上到右下
    //20 左下到右上
    //21 横条
    //22 竖条
    //23 以上22种随机选择一种
>#####MSThemeCompatible (XP主题)#####
*   说明：是否在IE中关闭 xp 的主题
*   注意：关闭 xp 的蓝色立体按钮系统显示样式，从而和win2k 很象。
*   用法：


    <Meta http-equiv="MSThemeCompatible" Content="Yes">
>#####Content-Script-Type (脚本相关)#####
*   说明：这是近来W3C的规范，指明页面中脚本的类型。
*   用法：


    <Meta http-equiv="Content-Script-Type" Content="text/javascript">