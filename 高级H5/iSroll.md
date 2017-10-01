# iScroll 的作用
```html
   	缩放
	拉动刷新
	速度和性能提升
	精确捕捉元素
	自定义滚动条
```

# iScroll 的使用方法
iScroll里的第一个参数很简单就是外容器的id
第二个参数允许你自定义一些属性配置和方法，比如下面的这段代码：

```js
<script>
	var myscroll=new iScroll("wrapper",{hScrollbar:false, vScrollbar:false});
</script>
```
 第二个参数通常都是一个对象，像上面的这个例子里就设定了不显示滚动条。所有参数如下（*号为常见参数）：

```html
hideScrollbar	是否隐藏滚动条	false 否 true 是	默认在Android上为false， iOS上为true
vScrollbar *	是否显示垂直滚动条	false 否 true 是	true
y	滚动垂直初始位置（负值）	数字值	0
onRefresh	refresh 的回调	null
onScrollStart	开始滚动的回调
onScrollMove	内容移动的回调
onScrollEnd	在滚动完成后的回调
```


## iScroll 方法API

```html
destroy
销毁你实例化的iScroll 实例，包括之前绑定的所有iscroll 事件。

refresh
这个方法非常有用，当你的滚动区域的内容发生改变 或是 滚动区域不正确，都用通过调用refresh 来使得iscroll 重新计算滚动的区域，包括滚动条，来使得iscroll 适合当前的dom。

scrollTo
这个方法接受4个参数 x, y, time, relative x 为移动的x轴坐标，y为移动的y轴坐标, time为移动时间，relative表示是否相对当前位置。

scrollToElement
这个方法实际上是对scrollTo的进一步封装，接受两个参数(el,time)，el为需要滚动到的元素引用，time为滚动时间。

scrollToPage
此方法接受三个参数(pageX,pageY,time) 当滚动内容的高宽大于滚动范围时，iscroll 会自动分页，然后就能使用scrollToPage方法滚动到页面。当然，当hscroll 为false 的时候，不能左右滚动。pageX这个参数就失去效果

disable
调用这个方法会立即停止动画滚动，并且把滚动位置还原成0，取消绑定touchmove, touchend、touchcancel事件。

enable
调用这个方法，使得iscroll恢复默认正常状态

stop
立即停止动画

zoom
改变内容的大小倍数,此方法接受4个参数，x,y,scale,time 分别表示的意思为，放大的基准坐标，以及放大倍数，动画时间

isReady
当iscroll 没有处于正在滚动，没有移动过，没有改变大小时，此值为true

```

#  实现原理

```js
	通过 topOffset 参数属性设置iScroll已经滚动的基准值；
	通过 onScrollMove 参数方法判断当前滚动是到顶端还是底端；
	通过 onScrollEnd 参数方法触发加载新数据，再通过 refresh 方法重新渲染界面；
	通过 onRefresh 参数方法调整刷新后的界面结构；
	<script>
		var myScroll =new iScroll("wrapper",{
			topOffset: 50,
			onRefresh: function(){...},
			onScrollMove: function(){...},
			onScrollEnd: function()...{}
		});
	</script>
```

```html
<div class="box">
    <div id="scroller">
        <ul>
            <li>sds50</li>
        </ul>
    </div>
</div>
```
## 1.iScroll需要对所要进行滚动的元素进行初始化
```js
<script src="iscroll.js"></script>
<script>
		var myscroll;
		function loaded(){
			setTimeout(function(){
				myscroll=new iScroll("wrapper");
			}，100 );
		}
		window.onload(loaded);
</script>

```
## 只有wrapper里的第一个子元素才可以滚动，如果你想要更多的元素可以滚动，那么你可以试试下面的这种写法：

```html
<div id="wrapper">
	<div id="scroller">
		<ul>
			<li></li>
			...
		</ul>
		<ul>
			<li></li>
			...
		</ul>
	</div>
</div>

```
