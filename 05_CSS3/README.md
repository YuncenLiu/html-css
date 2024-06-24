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


#### background-origin设置背景图

设置背景图的原点： `background-origin`

1. `padding-box` 从 padding 区域开始显示背景图（默认值）
2. `border-box` 从 border区域开始显示
3. `content-box` 从 content 区域开始显示

#### background-clip背景图裁切

作用：设置背景图的向外裁剪的区域

1. `border-box` 从 boxer 区域开始向外裁切（默认值）
2. `padding-box` 从 padding 区域开始
3. `content-box` 从 content 区域开始
4. `text` 背景图只呈现在文字上

> 若值为 text ，需要修改为 -webkit-background-clip

#### background-size背景图尺寸

设置背景图尺寸 `background-size`

1. 用长度指定背景图大小，不允许负值
	```css
	background-size: 400px 400px
	```
2. 用百分比指定背景图大小，不允许负值
	```css
	background-size: 100% 100%;
	```
3. `auto` 背景图真实大小，（默认值）
4. `contain` 背景图等比缩放，使背景图宽高与容器相等，可能会造成容器部分没有背景图片
	```css
	background-size: contain;
	```
5. `cover` 将背景图等比缩放，直到完全覆盖容器，（相对较好）
	```css
	background-size: cover;
	```

#### background复合属性

```css
background: color url repeat posistion / size origin clip
```

1. `origin` 和 `clip` 的值如果一样，如果只写一个值， 则 `origin` 和 `clip` 都设置，`origin` 必须写前面， `clip` 写后面
2. `size` 的值必须可在 `position` 的后面，并且用 / 分开

#### 多背景图


```css
background: url('../../doc/source/4_CSS3/images/bg-lt.png') no-repeat left top,  
url('../../doc/source/4_CSS3/images/bg-rt.png') no-repeat right top,  
url('../../doc/source/4_CSS3/images/bg-lb.png') no-repeat left bottom,  
url('../../doc/source/4_CSS3/images/bg-rb.png') no-repeat right bottom;
```

![多背景图](images/Pasted%20image%2020240624135729.png)

#### border-radius圆角边框

同时设置四个角：`border-radius: 50%;`

也可以分别设置，不过一般不用，`border-top-left-radius` ，一个值是正圆半径，两个值是椭圆的 x半径，y半径，然后还有 `border-top-right-radius`、`border-bottom-right-radius`、`border-bottom-left-radius` 根据瞬时间旋转形成的复合属性


#### 边框外轮廓

1. `outline-width` 外轮廓宽度
2. `outline-color` 外轮廓颜色
3. `outline-style` 外轮廓风格
	1. `none` 无轮廓
	2. `dotted` 点状
	3. `dashed` 虚线
	4. `solid` 实现
	5. `double` 双实线
4. `outline-offset `边框距离，正负都可以
5. `outline` 复合属性 `outline: 50px solid blud;`


### CSS3文本属性

#### text-shadow文本阴影

语法： `text-shadow：h-shadow v-shadow blur color;`

1. `h-shadow` 水平阴影，允许负值
2. `v-shadow `垂直阴影，允许负值
3. `blur` 模糊距离
4. `color` 颜色

#### white-space文本换行

1. `normal` 文本超出边界自动换行，文本中换行被浏览器识别为空格（默认值）
2. `pre` 原样输出，与 `pre` 标签效果相同
3. `pre-wrap` 在 `pre` 基础上，超出元素边界自动换行
4. `pre-line` 在 `pre` 基础上，超出边界自动换行，且识别文本中的换行，空格会忽略掉
5. `nowrap` 强制不换号

#### text-overflow文本溢出

1. clip 当内联内容溢出时，将溢出部分拆切掉（默认值）
2. ellipsis 当溢出时，将溢出部分替换为 ...

> 块容器必须定义为 overflow 为非 visible 值， white-space 为 nowrap 值才会生效

![text-overflow文本溢出](images/Pasted%20image%2020240624160414.png)

```css
ul {  
    width: 400px;  
    height: 400px;  
    border: 1px solid black;  
    margin: 100px auto;  
    font-size: 20px;  
    list-style: none;  
    padding: 10px;  
}  
  
li {  
    margin-bottom: 10px;  
    white-space: nowrap;  
    overflow: hidden;  
    text-overflow: ellipsis;  
}
```


#### text-decoration文本修饰

语法： `text-decoration: text-decoration-line  text-decoration-style  text-decoration-color`

1. `text-decoration-line` 线位置
	1. `none` 无修饰
	2. `underline` 下划线、`overline` 上划线、`line-through` 中划线
2. `text-decoration-style` 线条形状
	1. `solid` 实线（默认）
	2. `double` 双实线、`dotted` 点状线、`dashed` 虚线、`wavy` 波浪线
3. `text-decoration-color` 线颜色

#### 文本描边

目前只支持 -webkit- 内核浏览器

1. `-webkit-text-stroke-width` 文字描边宽度，长度
2. `-webkit-text-stroke-color` 颜色
3. `-webkit-text-stroke` 复合属性

```css
-webkit-text-stroke: 1px red;
```

### CSS3渐变

![](images/Pasted%20image%2020240624164036.png)

属性名： `background-image: linear-gradient()`

```css
.box1 {  
    background-image: linear-gradient(red, yellow, green);  
}  
  
.box2 {  
    background-image: linear-gradient(to right, red, yellow, green);  
}  
.box3 {  
    background-image: linear-gradient(20deg, red, yellow, green);  
}  
.box4 {  
    background-image: linear-gradient( red 50px, yellow 100px, green 150px);  
}  
.box5 {  
    background-image: linear-gradient(20deg, red, yellow, green);  
    text-align: center;  
    line-height: 200px;  
    font-weight: bold;  
    color: transparent;  
    -webkit-background-clip: text;  
}
```


径向渐变

```css
.box1 {  
    background-image: radial-gradient(red, yellow,green);  
}  
.box2 {  
    background-image: radial-gradient(at right top ,red, yellow,green);  
}  
.box3 {  
    background-image: radial-gradient(at 100px 50px ,red, yellow,green);  
}  
.box4 {  
    background-image: radial-gradient(circle ,red, yellow,green);  
}  
.box5 {  
    background-image: radial-gradient(200px 200px ,red, yellow,green);  
}  
.box6 {  
    background-image: radial-gradient(red 50px, yellow 100px ,green 150px);  
}  
.box7 {  
    background-image: radial-gradient(100px 50px at 150px 150px ,red 50px, yellow 100px ,green 150px);  
}
```


### web字体

> [阿里 定制字体网站](https://www.iconfont.cn/webfont#!/webfont/index) 