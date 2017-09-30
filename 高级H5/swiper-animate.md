## Swiper Animate使用方法
   Swiper Animate是Swiper中文网提供的用于在Swiper内快速制作CSS3动画效果的小插件
### 1. 使用Swiper Animate需要先加载swiper.animate.min.js和animate.min.css。

```html
<!DOCTYPE html>
<html>
<head>
    ...
    <link rel="stylesheet" href="path/to/swiper.min.css">
    <link rel="stylesheet" href="path/to/animate.min.css">
</head>
<body>
    ...
    <script src="path/to/swiper.min.js"></script>
    <script src="path/to/swiper.animate.min.js"></script>
</body>
</html>
```
###2. 初始化时隐藏元素并在需要的时刻开始动画。
```js
<script>        
	var mySwiper = new Swiper ('.swiper-container', {
	onInit: function(swiper){ //Swiper2.x的初始化是onFirstInit
	swiperAnimateCache(swiper); //隐藏动画元素 
	swiperAnimate(swiper); //初始化完成开始动画
	}, 
	onSlideChangeEnd: function(swiper){ 
	swiperAnimate(swiper); //每个slide切换结束时也运行当前slide动画
	} 
	})        
</script>
```
###3. 在需要运动的元素上面增加类名  ani   ，和其他的类似插件相同，Swiper Animate需要指定几个参数：
		swiper-animate-effect：切换效果，例如 fadeInUp 
		swiper-animate-duration：可选，动画持续时间（单位秒），例如 0.5s
		swiper-animate-delay：可选，动画延迟时间（单位秒），例如 0.3s
```html
<div class="swiper-slide">
	<p class="ani" swiper-animate-effect="fadeInUp" swiper-animate-duration="0.5s" swiper-animate-delay="0.3s">内容</p>
</div>
```