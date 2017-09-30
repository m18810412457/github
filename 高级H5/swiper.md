# swiper是什么？
  Swiper是纯javascript打造的滑动特效插件
# 有什么优点
  Swiper能实现触屏焦点图、触屏Tab切换、触屏多图切换等常用效果。
  Swiper开源、免费、稳定、使用简单、功能强大，是架构移动终端网站的重要选择！
 ## 使用方法
  1.首先加载插件，需要用到的文件有swiper.min.js和swiper.min.css文件。
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

2.初始化Swiper：最好是挨着</body>标签