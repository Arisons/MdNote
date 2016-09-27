####关于####
#####encodeURIComponent() / decodeURIComponent()#####
#####encodeURI() / decodeURI()#####
####区别####
>基本概念
>
>encodeURI和decodeURI是成对使用的，encodeURI把非英文转化为英文编码，decodeURI可以用来把字符串还原回来。encodeURIComponent() / decodeURIComponent()作用和encodeURI/decodeURI基本相同；
>
>但是encodeURI方法不会对下列字符进行编码：":"、"/"、";" 和 "?"，encodeURIComponent方法可以对这些字符进行编码。

>在获取地址栏中的地址是，因为浏览器的地址栏有中文会出现不可预期的错误（会发生什么事情呢？）。所以浏览器在访问一些有中文参数的链接时会先转码，所以在获取的时候要使用decodeURI()解码。

>前面在网上找了很多获取地址栏参数的方法，最后找到了这个。
>
	 function getUrlData(name){
                var reg = new RegExp("(^|&)"+name +"=([^&]*)(&|$)");
                var r = window.location.search.substr(1).match(reg);
                if( r!=null ){
                    return  unescape(r[2]);
                }else{
                    return null;
                }
            }
>它里面用的是unescape，通过测试其对中文不能解码。而且已经在ECMAscript v3中被废除。推荐大家使用 decodeURI()取代unescape()；详情参考[点击查看](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/unescape "MDN")；