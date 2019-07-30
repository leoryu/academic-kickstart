+++
title = "[Go的算法实现]数值的整数次方"
date = 2019-07-26T22:40:34+08:00
draft = false

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["algorithm", "go"]
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

剑指Offer中问题11的go实现。

<!--more-->

## 问题

> 给定一个double类型的浮点数base和int类型的整数exponent。求base的exponent次方。

## 思路

result(n) = result(n-1) *or/ result

使用递归即可。

## 注意点

- base为0
- base为负值
- exponent为0
- exponent为负值

## 代码实现

```go
package q011

func Answer(base float64, exponent int) (result float64) {
	if exponent == 0 {
		return 1
	}
	if exponent == 1 {
		return base
	}
	if exponent == -1 {
		return 1 / base
	}
	result = Answer(base, exponent>>1)
	result *= result
	if (exponent & 1) == 1 {
		result *= base
	}
	return
}
```
