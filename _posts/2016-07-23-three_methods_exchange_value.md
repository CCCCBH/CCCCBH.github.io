---
layout: post
title:  "值交换的三种方法"
date:   2016-07-23 09:54:00 +0800
categories: jekyll update
---
## 值交换 ##
	1.借助第三个变量来实现
	C=A; A=B; B=C;

	2.利用加减法实现两个变量的交换
	A=A+B; B=A-B; A=A-B;

	3.用位异或运算来实现，也是效率最高
	原理：利用一个数异或本身等于0和异或运算符合交换律。
	A=A^B; B=A^B; A=A^B;