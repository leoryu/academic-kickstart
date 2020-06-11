+++
title = "Vscode Vim常用技巧"
date = 2020-06-10T22:55:00+08:00
draft = false

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["vscode", "vim"]
categories = ["Tech"]

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
[image]
  # Caption (optional)
  caption = ""

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = ""
+++

Vscode可以通过安装Vim插件以实现在其中以Vim的方式编写代码，本文将介绍一些本人在使用中认为比较实用的一些Vim操作。

<!--more-->

未特殊说明的操作都是在normal模式下操作。

## 1. 移动

### 1.1. 翻页

组合键`crtl + f`可以向前翻页,`crtl + b`可以向前翻页。

此外可以使用`zt`、`zz`和`zb`实现以当前光标所在行为页顶、页中和页底重新调整页面位置。

### 1.2. 光标跳转

输入`_`和`$`可以将光标移动到行首和行尾。

输入`gg`和`G`分别可以跳到文件的首行和尾行。

输入`:numG`可以跳转到指定行。例如希望跳转到第10行就输入`10G`。

可以以百分比跳转到文件的指定位置。例如我想跳转到该文件的50%处时，可以输入`50%`。

可以使用数字结合`hjkl`操作光标。例如我想向上移动3行，可以输入`3k`。类似的`d3k`是向上删除3行（真灵活！）。

`mt`可以标记当前光标位置为`t`，`` `t``可以返回此位置。

## 2. 复制粘贴

### 2.1. 基础操作

`y`和`p`分别代码复制粘贴，`d`代表删除。

在此基础上有很多花样，例如`d3w`代表删除3个词，`y2l`代表复制两个字符等等。

### 2.2. 寄存器

寄存器的基本使用方法是使用`"{register}y`，然后使用`"{register}p`取出。其中`{register}`可以是a-z及A-Z。

此外还有一些特殊的寄存器。`"+p`可以去除剪切板内容，`":p`可以取出上一个Vim命令，`":p`可以取出上一次的搜索关键词。

