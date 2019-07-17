+++
title = "[Go的算法实现]斐波那契数列"
date = 2019-07-16T21:40:04+08:00
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

剑指Offer中问题9的go实现。

<!--more-->

## 问题

>大家都知道斐波那契数列， 现在要求输入一个整数n， 请你输出斐波那契数列的第n项。

## 思路

斐波那契数列可以用递归的方法求解，但是会有很多重复的计算。因此从前向后循环计算效率会好很多。

## 注意点

- 输入为0
- 输入为负数
- 输入为1
- 输入一个较大的数字

## 代码实现

```go
package q009

import (
	"math/big"
)

func Answer(n int) (numberN *big.Int) {
	num1 := big.NewInt(0)
	num2 := big.NewInt(1)
	if n <= 0 {
		return num1
	}
	if n == 1 {
		return num2
	}
	for i := 2; i <= n; i++ {
		tmpResult := big.NewInt(0)
		tmpResult.Add(num1, num2)
		num1 = num2
		num2 = tmpResult
	}
	return num2
}
```
