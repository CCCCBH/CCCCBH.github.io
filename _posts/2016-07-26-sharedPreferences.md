---
layout: post
title:  "SharedPreferences"
date:   2016-07-26 17:13:33 +0800
categories: jekyll update
---

### 将数据存储到SharedPreferences中 ###

	/**
	 * 1.调用SharedPreferences对象的edit()方法来获取一个SharedPreferences.Editor对象
	 * 2.向SharedPreferences.Editor对象中添加数据
	 * 3.调用commit()方法将添加的数据提交
	 */
	SharedPreferences.Editor editor = getSharedPreferences("data", MODE_PRIVATE).edit();
	
	editor.putString("name", "Tom");
	editor.putInt("age", 28);
	editor.putBoolean("married", false);
	
	editor.commit();

### 将数据存储到SharedPreferences中 ###

	/**
     * 1.通过getSharedPreferences()方法得到了SharedPreferences对象
     * 2.分别调用它的get方法(每种get方法都对应了SharedPreferences.Editor中的一种put方法)
     * 3.这些get方法接收两个参数：
     * 第一个参数是键 传入存储数据时使用的键就可以得到相应的值
     * 第二个参数是默认值 当传入的键找不到对应的值时的返回值
     */
     SharedPreferences preferences = getSharedPreferences("data", MODE_PRIVATE);

     String name = preferences.getString("name", " ");
     int age = preferences.getInt("age", 0);
     boolean married = preferences.getBoolean("married", false);