# swiper是什么？
  Swiper是纯javascript打造的滑动特效插件
# 有什么优点
  Swiper能实现触屏焦点图、触屏Tab切换、触屏多图切换等常用效果。
  Swiper开源、免费、稳定、使用简单、功能强大，是架构移动终端网站的重要选择！
 ## 使用方法
 ### 1.首先加载插件，需要用到的文件有swiper.min.js和swiper.min.css文件。
 ```html
 <!DOCTYPE html>
<html>
<head>
    ...
    <link rel="stylesheet" href="path/to/swiper.min.css">
</head>
<body>
   <div class="swiper-container">
    <div class="swiper-wrapper">
        <div class="swiper-slide">Slide 1</div>
        <div class="swiper-slide">Slide 2</div>
        <div class="swiper-slide">Slide 3</div>
    </div>
    <!-- 如果需要分页器 -->
    <div class="swiper-pagination"></div>
    <!-- 如果需要导航按钮 -->
    <div class="swiper-button-prev"></div>
    <div class="swiper-button-next"></div>
    <!-- 如果需要滚动条 -->
    <div class="swiper-scrollbar"></div>
</div>
    <script src="path/to/swiper.min.js"></script>
</body>
</html>

```js
## 2.初始化Swiper：最好是挨着</body>标签

<script>        
  var mySwiper = new Swiper ('.swiper-container', {
    direction: 'vertical',
    loop: true,//轮播是否自动循环
    autoplay: 5000,//自动切换的时间间隔（单位ms），不设定该参数slide不会自动切换。
     //你还可以在某个slide上设置单独的停留时间，例<div class="swiper-slide" data-swiper-autoplay="2000">
    initialSlide :2,//设定初始化时slide的索引。
    direction : 'vertical',//Slides的滑动方向，可设置水平(horizontal)或垂直(vertical)。
    autoplayDisableOnInteraction : false,//用户操作swiper之后，是否禁止autoplay。默认为true：停止。
    // 如果需要分页器
    effect : 'cube',//slide的切换效果，默认为"slide"（位移切换），可设置为"fade"（淡入）"cube"（方块）"coverflow"（3d流）"flip"（3d翻转）。
    pagination: '.swiper-pagination',
    
    // 如果需要前进后退按钮
    nextButton: '.swiper-button-next',
    prevButton: '.swiper-button-prev',
    
    // 如果需要滚动条
    scrollbar: '.swiper-scrollbar',
  })        
  </script>

```
## 注意: 页面加载完成后再初始化。 
<script type="text/javascript">
	window.onload = function() {
	  ...
	}
</script> 

或者

<script type="text/javascript">
	$(document).ready(function () {
	 ...
	})
</script>