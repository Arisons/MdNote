####如何利用margin负值实现常用布局####
>margin实现两端对齐的布局
>
>通过margin-right改变元素的空间来实现，margin-right负值改变元素的占用空间，使得box元素在右边预留出20px的空间
>
	<style>
		.box{
			width: 1200px;
			margin: auto;
			background: orange;
		}
		.ul {
			overflow: hidden;
			margin-right: -20px;
		}
		.li {
			width: 380px;
			height: 300px;
			margin-right: 20px;
			background: green;
			float: left;
		}
	</style>
	<div class="box">
		<div class="ul">
			<div class="li">列表1</div>
			<div class="li">列表2</div>
			<div class="li">列表3</div>
		</div>
	</div>
>margin负值下的等高布局
>
>利用margin可以改变元素的占用空间
>
	<style>
		.box {
			overflow: hidden;
			resize: vertical;
		}
		.orange, .green {
			margin-bottom: -600px;
			padding-bottom: 600px;
		}
		.orange {
			float: left;
			background: orange;
		}
		.green {
			float: left;
			background: green;
		}
	</style>
	<div class="box">
		<div class="orange">
			<div>左黄</div>
			<div>左黄</div>
			<div>左黄</div>
			<div>左黄</div>
		</div>
		<div class="green">
			<div>右绿</div>
			<div>右绿</div>
		</div>	
	</div>