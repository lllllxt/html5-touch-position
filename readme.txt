Html5 -- touch事件基础之获取触摸点位置


笔记：

移动端触屏滑动的效果其实就是图片轮播，在PC的页面上很好实现，绑定click和mouseover等事件来完成。但是在移动设备上，要实现这种轮播的效果，就需要用到核心的touch事件。处理touch事件能跟踪到屏幕滑动的每根手指。
以下是四种touch事件
touchstart: //手指放到屏幕上时触发
touchmove: //手指在屏幕上滑动式触发
touchend: //手指离开屏幕时触发
touchcancel: //系统取消touch事件的时候触发，这个好像比较少用
每个触摸事件被触发后，会生成一个event对象，event对象里额外包括以下三个触摸列表
touches: //当前屏幕上所有手指的列表
targetTouches: //当前dom元素上手指的列表，尽量使用这个代替touches
changedTouches: //涉及当前事件的手指的列表，尽量使用这个代替touches
这些列表里的每次触摸由touch对象组成，touch对象里包含着触摸信息，主要属性如下：
clientX / clientY: //触摸点相对浏览器窗口的位置
pageX / pageY: //触摸点相对于页面的位置
screenX / screenY: //触摸点相对于屏幕的位置
identifier: //touch对象的ID
target: //当前的DOM元素
注意：
手指在滑动整个屏幕时，会影响浏览器的行为，比如滚动和缩放。所以在调用touch事件时，要注意禁止缩放和滚动。
1.禁止缩放
通过meta元标签来设置。
2.禁止滚动
preventDefault是阻止默认行为，touch事件的默认行为就是滚动。
event.preventDefault();