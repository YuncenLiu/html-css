# CSS3

## CSS3简介

### CSS3私有前缀

如下代码中 `-webkit-` 就是私有前缀

```css
div {
	width:400px;
	height: 400px;
	-webkit-border-radius: 20px;
}
```

W3C 标准所提出的某个 CSS 特性, 在被浏览器正式支持之前, 浏览器厂商会根据浏览器的内核, 使用私有前缀来测试改 CSS 特性,在浏览器正式支持 CSS 特性后,就不需要私有前缀了.

查询 CSS3 兼容性的网站 [http://caniuse.com](http://caniuse.com)

1. `Chrome` 浏览器: `-webkit-`
2. `Safari` 浏览器 `-webkit-`
3. `Firefox` 浏览器 `-moz-`
4. `Edge` 浏览器 `-webkit-`
5. 旧 `Opera` 浏览器 `-o-`
6. 旧 `IE` 浏览器 `-ms-`

举例子,按顺序写

```css
-webkit-border-radius: 20px;
-moz-border-raidus: 20px;
-mz-border-radius: 20px;
-o-border-radius: 20px;
border-radius: 20px
```

### CSS3新增长度

1. `rem` 根元素字体大小的倍数,只与根元素字体大小有关
2. `vm` 视口宽度的百分之多少, 10vm 就是视口宽度的 10%
3. `vh` 视口高度的百分之多少, 10vh 就是视口高度的 10%
4. `vmax` 视口宽高中最大的那个百分比, vmin 含义相似

### CSS3新增盒模型

#### box-sizing怪异盒子模型

属性:  `box-sizing: border-box;` 

1. `content-box` 默认值, `width` 和 `height` 是盒子内容区的大小
2. `border-box` 是盒子的总大小,会 压缩 `padding` 和 `border` 的值

#### resize调整盒子大小

使用 `resize: both;` 设置用户是否直接在页面上调整尺寸

1. `none` 不允许(默认值)
2. `both` 宽高都可以调整
3. `horizontal` 只可以调整宽度, `vertical` 只可用调整宽

注意, 需要在当前被调整元素添加 `overflow` 元素才会生效 原因是因为如果存在子元素超出当前元素的情况下, 是否展示与滚动条的问题.

> 实际没啥用

#### box-shadow

为盒子添加阴影

语法: `box-shadow: h-shadow v-shadow blur spread color inset;`

1. `h-shadow` 水平阴影,必须写,可用为负数
2. `v-shadow` 垂直阴影,必须写,可用为负数
3. `blur` 可选,模糊距离
4. `spread` 可选,阴影外延值
5. `color` 可选,阴影颜色
6. `inset` 可选, 将外部阴影改为内部阴影

`box-shadow: none;` 表示没有阴影, 配合 `position`. `transition` 效果更佳


```css
.box2 {  
    height: 200px;  
    width: 200px;  
    margin: 0 auto;  
    background-color: skyblue;  
    position: relative;  
    transition: 100ms linear all;  
  
}  
.box2:hover {  
    top: -5px;  
    left: 0;  
    box-shadow: 10px 10px 20px -10px black;  
}
```


#### opacity不透明度

`opacity` 属性能为整个元素添加透明效果,值是 `0 - 1 ` 之间的小数, `0`  是完全透明, `1` 是完全不透明

> `opacity` 与 `rbga` 的区别? `opacity` 是一个 css3 的属性, 设置的是整个元素,包括元素里的内容的不透明度, `rgba` 用于设置颜色,仅仅是调整颜色的不透明度