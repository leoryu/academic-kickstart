+++
title = "[Go的算法实现]反转列表"
date = 2019-08-31T22:47:00+08:00
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

剑指Offer中问题16的go实现。

<!--more-->

## 问题

> 输入一个链表，反转链表后，输出链表的所有元素。

## 思路

新建一个指针作临时存储用。

## 注意点

- 空链表
- 只有一个节点的链表

## 代码实现

```go
package q016

type NodeList struct {
	Value    int
	NextNode *NodeList
}

func Answer(head *NodeList) (target *NodeList) {
	if head == nil || head.NextNode == nil {
		return head
	}
	var tmpNode *NodeList
	for head != nil {
		next := head.NextNode
		head.NextNode = tmpNode
		tmpNode = head
		head = next
	}
	return tmpNode
}
```
