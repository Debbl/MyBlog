---
title: "初识CSS"
top_img: './初识CSS/images/css-logo.png'
cover: './初识CSS/images/css-logo.png'
tags:
  - Web
  - CSS
categories:
  - Web
  - CSS
description: CSS 的三种引入方式和其他知识
abbrlink: '657'
date: 2021-09-11 23:20:50
updated: 2021-09-11 23:20:50
---

# 初识 CSS

HTML用于定义内容的结构和语义，CSS Cascading Style Sheets **层叠样式表** 用于设计风格和布局。比如，您可以使用 CSS 来更改内容的字体、颜色、大小、间距，将内容分为多列，或者添加动画及其他的装饰效果。

## 如何将 CSS 样式应用到元素上

- 内联样式 `inline style`
- 文档样式表 `document style sheet`、内嵌样式表 `embed style sheet`
- 外部样式表 `external style sheet`

### 内联样式 inline style

> 将样式直接写在元素的 style 属性上

```html
<div style="color: white; background: red">显示文字</div>
```

### 文档样式表 document style sheet

> style 元素的 `type` 属性默认值是 `text/css`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style type="text/css">
        div {
            color: white;
            background-color: red;
        }
    </style>
</head>
<body>
    <div>显示文字</div>
</body>
</html>
```

### 外部样式表 external style sheet

> 将样式写在一个单独的 css 文件，在当前文档的 head 元素中的 link 标签引入

- link 引入样式

> index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <link rel="stylesheet" href="./style.css">
</head>
<body>
    <div>显示文字</div>
</body>
</html>
```

> style.css

```css
div {
    color: white;
    background-color: red;
}
```

- style 的 @import 引入样式

> index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        @import url("./style.css");
    </style>
</head>
<body>
    <div>显示文字</div>
</body>
</html>
```

> @import 导入的效率比 link 低

## 一些补充

### 设置网页图标

> rel 属性不能省略，图标的格式可以是 ico、png，常用大小是 16×16、24×24、32×32 像素

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <link rel="shortcut icon" href="https://gitee.com/Debbl/hexo-blog-imges/raw/master/images/favicon.png" type="image/x-icon">
    <style>
        @import url("./style.css");
    </style>
</head>
<body>
    <div>显示文字</div>
</body>
</html>
```

### 常用 CSS 属性

- 文本

color、direction、letter-spacing、word-spacing、line-height、text-align、text-indent、text-transform、text-decoration、white-space

- 字体

font、font-family、font-style、font-size、font-variant、font-weight

- 背景

background、background-color、background-image、background-repeat、background-attachment、background-position

- 盒子模型

width、height、border、margin、padding

- 列表

list-style

- 表格

border-collapse

- 显示

display、visibility、overflow、opacity、filter

- 定位

vertical-align、position、left、top、right、bottom、float、clear

### 关于 CSS 中的颜色

颜色多种表示方法

- 基本颜色关键字

**red** 红色 **green** 绿色 **blue** 蓝色 等等

- RGB 颜色

  - 十进制表示

  > 三个参数分别代表 red、green、blue 的颜色程度值在 0-255 之间

  ```text
  rgb(255, 255, 255)
  <!-- 这个是白色 -->
  ```

  - 十六进制表示

  > 0-255 转换为十六进制是 0x00-0xff

  ```text
  #FFFFFF
  <!-- 这个是白色 -->
  #FFF
  <!-- 简写,使用简写可以节省资源 -->
  ```

- RGBA 颜色

> 比 RGB 多加了一个 alpha，表示透明度，0.0-1.0，0 表示完全透明，1 表示完全不透明

```text
rgba(0, 0, 255, 0.5)
```

### 一些链接

- 官方文档
  - https://www.w3.org/TR/?tag=css
  - https://www.w3.org/TR/CSS22/
  - https://www.w3.org/TR/CSS22/propidx.html
- 查看 CSS 属性浏览器兼容性
  - https://caniuse.com/
