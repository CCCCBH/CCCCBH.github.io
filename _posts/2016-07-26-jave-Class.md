---
layout: post
title:  "Class类的使用"
date:   2016-07-26 15:27:29 +0800
categories: jekyll update
---

	万事万物皆对象
	静态成员不是对象
	普通数据类型不是对象
	类是对象
	类是java.lang.Class类的实例对象

### 三种方法表达Class类 ###

	public class Test {
	
		public static void main(String[] args) {
	
			// Foo的实例对象如何表示
			Foo foo1 = new Foo();
			// Foo这个类 也是一个实例对象 Class类的实例对象 如何表示呢
			// 任何一个类都是Class类的实例对象 三种方法
	
			// 第一种表达方式--->实际在告诉我们任何一个类都有一个隐含的静态成员变量
			Class class1 = Foo.class;
	
			// 第二张表达方式--->已经知道该类的对象通过getClass方法
			Class class2 = foo1.getClass();
	
			// 第三张表达方式--->
			try {
				Class class3 = Class.forName("完整的类名");
			} catch (ClassNotFoundException e) {
				e.printStackTrace();
			}
	
			/*
			 * class1 class2表示了Foo类的类类型(class type) 类也是对象 是Class类的实例对象
			 * 这个对象我们称为该类的类类型
			 */
	
			try {
				Foo foo2 = (Foo) class1.newInstance();
			} catch (InstantiationException e) {
				e.printStackTrace();
			} catch (IllegalAccessException e) {
				e.printStackTrace();
			}
	
		}
	}
	
	class Foo {}