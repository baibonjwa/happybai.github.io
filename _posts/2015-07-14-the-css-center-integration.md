---
layout: post
title: CSS居中的方法整合--水平居中
date: 2015-07-14T9:24:13+08:00
summary: CSS居中的方法整合--水平居中
categories: 前端
---

CSS的居中问题，是一个老生常谈的问题，各种居中方法层出不穷。是水平居中还是垂直居中？是block还是inline？
居中对象是一个还是多个？长度宽度是否确定？等等各种因素确定。

这里就从这些方面对这些各种CSS的居中方法进行一些整理。

# 1.1 inline类型元素
对于inline类型的元素，在上级div使用text-align属性是很不错的选择
(其中inline类型可以包括inline, inline-block, inline-table, inline-flex)
{% highlight css %}
.parent {
  text-align: center;
}
{% endhighlight %}
[Example](https://jsfiddle.net/happybai/5c9pt7h8/1/)

# 1.2 block类型元素
对于block类型的元素，可以对要居中的元素使用margin: 0 auto;属性
但这种情况需要为block类型的元素设置一个宽度，否则这个元素会填满整个上级div
{% highlight css %}
.child {
  margin: 0 auto;
}
{% endhighlight %}
[Example](https://jsfiddle.net/happybai/h3wenhhk/)

如果不设置宽度，也有种办法实现居中，就是将居中元素的display属性设置为table

[Example](https://jsfiddle.net/happybai/n5a79p2f/)

# 1.3 多个block类型元素 
如果有多个block级元素排列成一行（注意是排列成一行）并且居中，这时需要改变一下block元素的类型，可以使用inline-block和flex两种方法实现
inline-block:
{% highlight css %}
.parent {
  text-align: center;
}
.child {
  display: inline-block;
}
{% endhighlight %}
[Example](https://jsfiddle.net/happybai/n5a79p2f/2/)

flex:
{% highlight css %}
.parent {
  display: flex;
  justify-content: center;
}
{% endhighlight %}
[Example](https://jsfiddle.net/happybai/n5a79p2f/3/)

如果多个block元素排成一竖列并且居中，这时使用margin:0 auto即可实现
如果div无固定宽度，可以使用display:table属性

有固定宽度:

[Example](https://jsfiddle.net/happybai/n5a79p2f/4/)

无固定宽度:

[Example](https://jsfiddle.net/happybai/n5a79p2f/5/)
