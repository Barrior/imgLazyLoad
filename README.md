# imgLazyLoad
基于jQuery的一个简洁高效的图片延时加载插件

###插件使用方法：
> 假设body内容如下：

    <body>
	    <img data-src="xxx.jpg" src="loading.gif" />
	    <img data-src="xxx.jpg" src="loading.gif" />
	    ...
	</body>
	
    data-src里是图片的真实地址
    src里是转圈圈的loading动画的地址


> js方面，先后引入jquery.js，imglazyload.js文件，如下API使用即可实现图片延时加载的效果。
更详细的了解可以查看Demo.html，或者js源码。

	$('img').imgLazyLoad({
		//触发滚动事件的容器，默认为window，参数为jQuery选择器字符串或对象
		container: window,
		//默认'fadeIn(淡入)',参数为jQuery默认效果，如show，slideDown等
		effect: 'fadeIn',
		//动画运行时间，默认600ms，参数为jQuery效果的速度
		speed: 600,
		//当用户看到图片时，是否立即加载图片，默认延迟400ms(即滚动延迟400ms)，参数类型为number
		delay: 400,
		//每次图片显示完毕后的回调函数
		callback: function(){

			$( this ).css( 'opacity', .99 );

		}
	});
