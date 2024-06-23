# HTML5

## HTML5简介

### HTML5优势

1. 针对 `Javascript` 新增了很多可操作接口
2. 新增了一些语义化标签，全局属性
3. 新增了多媒体标签，可以很好的替代 `flash`
4. 更加侧着语义化，对 `SEO` 更友好
5. 可移植性好，可以大量应用在移动设备上

### HTML5兼容性

支持 Chrome、Safari、Opera、Firefox 主流浏览器

> IE 浏览器必须是 9 及以上版本才支持 HTML5，且 IE9 仅支持部分 HTML新特性

## 新增语义化标签

### 新增布局标签

1. `header` 整个页面，或部分区域的头部
2. `footer` 整个页面，或部分区域的底部
3. `nav` 导航
4. `article` 文章、帖子、杂志、新闻、博客
5. `section` 页面中的某些文字
6. `aside` 侧边栏
7. `main` 文档主要内容（几乎不用）
8. `hgroup` 包括连续的标题，如文章主标题，副标题组合（W3C将其删除）

关于 `article` 和 `section`
1. `article` 里面可以有多个 `section`
2. `section` 强调的是分段或者分快，如果你想将一块内容分成几段的时候，可以用 `section` 元素
3. `article` 比 `section` 更强调独立性，一块内容如果比较独立，比较完整，应该使用 `article` 元素


### 新增状态标签

#### meter标签

定义已知范围内的标量测量, 也被称为 gauge 尺度, 双标签, 例如: 电量，磁盘用量等

1. `high`  规定高度
2. `low`  规定低度
3. `max` 规定最大
4. `min`  规定最小值
5. `optimum`  规定最优值
6. `value`  规定当前值

#### progress标签

显示某个人物完成的进度的指示器, 一般用于表示进度条, 双标签, 例如:  工作完成进度等

1. `max` 规定目标值
2. `value` 规定当前值


### 新增列表标签

1. `datalist` 用于搜索框的关键字提示
2. `details` 用于问题和答案, 或对专有名词进行解释
3. `summary` 写在 `details` 里面,用于指向问题或专有名词

不同浏览器对 `datalist` 渲染效果可能不同

```css
<form action="#">  
    <input type="text" list="mydata">  
    <button>搜索</button>  
</form>  
<datalist id="mydata">  
    <option value="周杰伦">周杰伦</option>  
    <option value="周冬雨">周冬雨</option>  
    <option value="马冬梅">马冬梅</option>  
    <option value="温兆伦">温兆伦</option>  
</datalist>
```

```html
<details>  
    <summary>如何一夜暴富</summary>  
    <p>来敲代码吧</p>  
</details>
```

### 新增文本标签

#### 文本注音

1. `ruby` 包裹需要注音的文字
2. `rt` 写拼音, `rt` 标签写在 `ruby` 里面
 
```css
<ruby>  
    <span>魑魅魍魉</span>  
    <rt>chī mèi wǎng liǎng</rt>  
</ruby>
```

[文字转换拼音网站](https://www.aies.cn/pinyin2.htm)
#### 文本标记

`mark` 标记, W3C 建议 mark 用标记搜索结果中的关键词

### 新增表单控件

#### 表单控件新增属性

1. `placeholder` 提示文字(注意, 不是默认值, value 是默认值), 适用于文字输入类的表单空间
2. `required` 表示该输入项必填,适用于除按钮外其他表单空间
3. `autofocus` 自动获取焦点,适用于所有表单控件
4. `autocomplete` 自动完成, 可用设置为 `on` 或 `off`,使用于 文字输入类的表单控件.密码框, 多行输入框不可用
5. `pattern` 正则表达式, 多行输入框不可用, 空输入框不会验证, 通常与 `required` 一起用

[Url转码网站](https://www.wetools.com/url-encode)

#### input新增属性值

1. `emial` 邮件类型输入框
2. `url` 网址类输入框
3. `number` 数字类输入框,有 step 步长属性,移动端也会唤起数字键盘
4. `search` 搜索类输入框, 会有一个清空按钮
5. `tel` 电话类输入框,移动端键盘时,会唤起数字键盘
6. `range` 范围输入框, 一个可拉动的进度条
7. `color` 颜色选择器
8. 日期选择器
	1. `date` 日期选择器, yyyy-MM-dd 格式
	2. `month` 月份选择器  yyyy-MM 格式
	3. `week` 周选择器 yyyy-WW 格式
	4. `time` 时间选择器 hh:mm 格式
	5. `datetime-local` 日期+时间格式, yyyy-MM-dd hh:mm:ss 格式

`from` 标签新增属性名 `novalidate` 如果用了上述验证形表单,使用此属性,将不再进行验证



### 音频控件
#### 视频标签

`video`  标签用来定义视频

1.  `src` 视频的 url 地址
2. `widht` `height` 宽, 长 像素值
3. `controls` 视频控件,播放, 暂停按钮
4. `muted` 视频静音
5. `autoplay` 视频自动播放, 绝大部分浏览器要求,设置视频静音后才可以自动播放, 也可以通过 `chrome://media-engagement/` 查看浏览器
6. `loop` 循环播放
7. `poster` 视频封面
8. `preload` 视频预加载, 使用自动播放可用忽略
	1. `none` 不预加载
	2. `metadata` 仅预先获取视频的元数据
	3. `auto` 下载整个视频文件,即使用户不希望使用它


#### 音频标签

`audio`  标签用来定义音频

1. `src` 音频 url 地址
2. `controls` 音频控件播放, 暂停按钮
3. `autoplay` 自动播放
4. `muted` 静音
5. `loop` 循环播放
6. `preload` 预加载 和视频的这个属性一致

### 新增全局属性

1. `contenteditable`  该元素是否被用户修改, true 可编辑, false 不可编辑
2. `draggable` 该元素可以被拖动, true 可用,false 不可用
3. `hidden` 隐藏元素
4. `spellcheck` 规定是否对元素进行拼音和语法检查, true 检查, false 不检查
5. `contextmenu` 规定元素的上下文菜单,在用户鼠标右键点击元素时显示
6. `data-*` 用于存储页面的是有定制数据

### HTML5兼容性

1. 添加元信息,让浏览器处于最优渲染模式
	```html
<!-- 让IE浏览器处于一个最优的渲染模式 -->  
<meta http-equiv="X-UA-Compatible" content="IE=edge">  
<!-- 针对一些国产的“双核”浏览器的设置，让浏览器优先使用webkit内核去渲染网页 -->  
<meta name="render" content="webkit">
```
2. 使用 html5shiv 让浏览器认识 H5 语义化标签
```html
<!--[if lt ie 9]>  
<script src="./html5shiv.js"></script>  
<![endif]-->
```

