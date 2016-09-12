####移动端-输入法挡住输入框解决办法####
	$("input").focus(function(){
		var top = $(this).offset().top;
		setTimeout(function(){
			$(window).scrollTop( top );
		},500)
	})

>这里给了一个延迟

我在自己的代码测试的时候发现获取页面高度会获取两次，肯能第一次获取的时候*输入框*距离页面顶部距离还没变，而第二次的时候才发生变化。所以才给了0.5s的延迟。（有待进一步测试。。。）
