# HTML

## 1、基础概念

### 1.1、文档声明

`<!DOCTYPE html>` 指的是 H5

不同版本的标识各不一致，可以通过官网查询 [https://www.w3.org/QA/2002/04/valid-dtd-list.html](https://www.w3.org/QA/2002/04/valid-dtd-list.html)

### 1.2、字符集

+ ASCII：大写字母、小写字母、数字、符号等一共128个
+ ISO 8859-1: 在 ASCII，扩充了希腊字符，共计 256个
+ GB2312: 继续扩充，收录 6763个常用汉字，682个字符（生僻字不包含）
+ GBK：收录了汉字和符号达到 20000+，支持繁体中文
+ UTF-8：万国码，包含世界上所有语言的：所有字符与符号

1. 如果是使用低版本保存文件，文件就直接废了，无法修复。
2. 如果是使用错误的解码方式打开文件，发现乱码，是可以补救的。

在 html 通过 `<meta charset="UTF-8">` 告知浏览器用 utf8 编码和解码，如果不写，默认使用 utf-8，如果乱写成其他格式，不适用工具的情况下，必定乱码。大写 `UTF-8` 和小写 `utf-8` 对浏览器无感

### 1.3、语言代码

第一种写法，（语言-国家/地区）
+ en：英文
+ zh-CN：简体中文
+ zh-TW：繁体中文
+ zh：中文
+ en-US：英语-美国
+ en-GB：英语-英国

```html
<html lang="en">
```

【W3School】

[HTML 语言代码参考手册](https://www.w3school.com.cn/tags/html_ref_language_codes.asp)

[HTML ISO 国家/地区代码参考手册](https://www.w3school.com.cn/tags/html_ref_country_codes.asp)

【W3C】

[Language tags in HTML and XML](https://www.w3.org/International/articles/language-tags/)