---
title: hexo设置
date: 2020-12-23 22:45:26
updated: 2020-12-26 14:32:00
description: 关于hexo的设置以及next主题的优化
category: 博客设置
---
## add custom pages in menu.

创建一个新页面

在 next/_config.yml 的 menu 中添加page即可

## 动画

motion设置中 enable:false

## back2top

scrollpercent设置不知为何在github pages里不起作用


## copy_button

github pages 
default 不起作用
flat 可用

## 显示摘要

对next主题有两种方式，首先打开设置。

```
excerpt_description: true
```

之后在post里需要设置

### 方法一：写概述

在文章的front-matter中添加description，其中description中的内容就会被显示在首页上，其余一律不显示。

```
title: 让首页显示部分内容
date: 2020-12-26 09:54:10
description: 这是显示在首页的概述，正文内容均会被隐藏。
```

### 方法二：文章截断

在需要截断的地方加入：

```
<!-- more -->
```

发现一个写的很好的说明[文章](https://zhuanlan.zhihu.com/p/30836436)