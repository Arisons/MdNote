####解a标签包裹图片，点击是出现蓝色边框问题####
>引入如下a标签样式即可

	a  {
		tap-highlight-color: rgba(0,0,0,0);
		focus-ring-color: rgba(0, 0, 0, 0);  
		-webkit-tap-highlight-color: rgba(0,0,0,0);  
		-webkit-focus-ring-color: rgba(0, 0, 0, 0);  
		-moz-tap-highlight-color: rgba(0,0,0,0);  
		-moz-focus-ring-color: rgba(0, 0, 0, 0); 
	}