### 常用标签补充

+ pre 按原文显示（一般用于页面中潜入大段代码）

### 表单

1. from 表单
    1. action 用于指定表单提交地址
    2. target 用于控制表单提交后，如何打开页面
        1. _self 在本地窗口打开
        2. _blank 在新窗口打开
    3. method 打开方式 post、get
2. input 输入框
    1. type 设置输入框类型
    2. name 用于指定提交数据名字
3. button 按钮

```html

<form action="https://www.baidu.com/s">
    <!--  wd 是百度定义的搜索关键词 date:2024-6-14 -->
    <input type="text" name="wd">
    <button>百度搜索</button>
</form>
<form action="https://search.jd.com/search" target="_blank" method="get">
    <!--  keyword 是京东定义的搜索关键词 date:2024-6-14 -->
    <!--  云：需要跳转登录页面后才可以搜索 date-:2024-6-14 -->
    <input type="text" name="keyword">
    <button>京东搜索</button>

</form>
```

#### 常用表单控件

1. name 数据名称
2. value 输入框默认值
3. maxlength 输入框最大可输入长度
4. type 输入框类型 【text、password、radio、checkbox、hidden、submit、reset、button】

隐藏域： type="hidden" 用户不可见区域，作用：提交表单时，携带一些固定的数据

普通按钮： type="button" 点击不会引起表单提交（submit）和表单重置（reset），不写默认为 submit 引起表单提交

点击文字 input 框获取焦点 `label`,用法：

```html
    <label for="account">账户：</label>
<input id="account" type="text" name="keyword" value="" maxlength="10">
```

虽然按钮也可以实现 label 关联，但是很怪异，一般没人这么干。

#### iframe

引入其他页面，使用 a 标签触发显示

```html
<a href="https://www.liuyuncen.com" target="container">点我进主页</a>
<br>
<form action="https://so.toutiao.com/search" target="container">
    <input type="text" name="keyword">
    <input type="submit" value="搜索">
</form>
<br>
<iframe name="container" frameborder="0" width="1200" height="400"></iframe>
```

#### 字符实体

在 HTML，用特殊代码描述一个符号

+ ` ` 空格：&nbsp;、&#160;
+ `<` 小于号：&lt;
+ `>` 大于号：&gt;
+ `&` 和号：&amp;

### HTML全局属性

+ id 唯一标识，不能重复，不能在 head、html、meta、title、script、style 元素中使用
+ class 类名
+ style 样式
+ dir 内容方向 ltr、rtl
+ title 设置文字提示，一般超链接和图片用的多
+ lang 给标签设定语言

### meta元信息

```html

<meta charset="UTF-8">
<!--   针对IE 浏览器兼容设置 -->
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<!--    移动端配置-->
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<!-- 网页关键字 -->
<meta name="keywords" content="8-12个英文逗号隔开的单词/词语">
<!-- 网页描述信息 -->
<meta name="description" content="80字以内的一句话，与网站内容相关">
<!-- 针对搜索引擎爬虫配置 -->
<meta name="robots" content="">
<!-- 配置网页作者 -->
<meta name="author" content="yun">
<!-- 网页生成工具 -->
<meta name="generator" content="WebStorm">
<!-- 网页版权信息 -->
<meta name="copyright" content="2023-2027©版权所有">
<!-- 网页自动刷新 真的会自动跳转 这种跳转不能后退，如果不配置url 就是原地跳转 -->
<meta http-equiv="refresh" content="10;url=https://www.baidu.com">
```

爬虫配置表
+ index：允许搜索爬虫索引
+ noindex：要求搜索爬虫不索引次页面
+ follow：允许搜索爬虫跟随此页面上链接
+ nofollow：要求搜索爬虫不跟随此页面链接
+ all：与 index、follow 等价
+ none： 与 noindex、nofollow 等价
+ noarchive：要求搜索引擎不缓存页面内容
+ nocache：noarchive 题代名词
