# lol-homePage

英雄联盟官网首页静态页面,纯 html,css(less). 

**只是将less引入到本地,lessc.js文件,唯一的js文件**

基本做到还原(热门活动结构--新皮肤模块一部分功能需要js,没有实现)

* 运行方式: clone下来后,双击index.html就可以了

* 网页结构如下

```
头部: header

头部广告: header-ad

新闻-热门活动: main

​ 新闻: new

​ 热门活动: hot-ac

视屏: video

赛事中心: match

英雄资料: hero-data

FANART 创作馆: fanart

底部: footer

侧边固定栏: r-nav
```

##### 难点

英雄资料部分,做单击变化

利用 label input 的特性

label 和 input 可以通过 for 和 id 实现绑定

```html
<label for="tab1">
  <input type="radio" name="tab" id="tab1" />
</label>

这样也是可以选中的
<input type="radio" name="tab" id="tab1" />
<div class="ttta">
  <label for="tab1"></label>
</div>
:checked 这个伪类表示任何处于选中状态的radio 普遍兄弟选择器 ~ 
(要注意的是,这里只会选择后面的元素,在前面的不会被选中)
#tab1:checked~.hero-occ 
具体代码在index.html的1054行后 + hero-data.less文件
```

滚动条,要用到伪元素(百度的)

```css
//修改滚轮样式
&::-webkit-scrollbar{
  width: 5px;
}
&::-webkit-scrollbar-thumb {
  border-radius: 10px;
  background-color: #abc0c3;
}
&:hover::-webkit-scrollbar{
  width: 10px;
}
```
