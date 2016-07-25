---
layout: post
title:  "ActionBar"
date:   2016-07-23 18:01:09 +0800
categories: jekyll update
---
# ActionBar #

## 在ActionBar上添加按钮 ##

	<!--如果ActionBar空间足够则显示-->
    android:showAsAction="ifRoom"
    <!--一直显示在ActionBar上-->
    android:showAsAction="always"
    <!--不显示在ActionBar中 折叠在OverFlow里-->
    android:showAsAction="never"
    <!--菜单项和它的图标 菜单文本一起显示-->
    android:showAsAction="withText"

## 自定义ActionBar ##

### 方法一 ###
创建一个actionbar.xml

	<?xml version="1.0" encoding="utf-8"?>
	<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
	    android:layout_width="match_parent"
	    android:layout_height="match_parent"
	    android:orientation="horizontal">
	
	    <Button
	        android:id="@+id/action_bar_left"
	        android:layout_width="wrap_content"
	        android:layout_height="wrap_content"
	        android:layout_gravity="center"
	        android:background="@android:color/transparent"
	        android:gravity="left|center_vertical"
	        android:text="Left" />
	
	    <TextView
	        android:id="@+id/action_bar_title"
	        android:layout_width="0dp"
	        android:layout_height="wrap_content"
	        android:layout_gravity="center"
	        android:layout_weight="1"
	        android:gravity="center"
	        android:textSize="24sp" />
	
	    <Button
	        android:id="@+id/action_bar_right"
	        android:layout_width="wrap_content"
	        android:layout_height="wrap_content"
	        android:layout_gravity="center"
	        android:background="@android:color/transparent"
	        android:gravity="right|center_vertical"
	        android:text="Right" />
	</LinearLayout>

在onCreate方法中调用下列方法创建一个自定义的actionbar

	getSupportActionBar().setDisplayOptions(ActionBar.DISPLAY_SHOW_CUSTOM);
	getSupportActionBar().setCustomView(R.layout.actionbar);

不需要的左Button或右Button调用下列方法隐藏

	mButtonLeft.setVisibility(View.INVISIBLE);
	mButtonRight.setVisibility(View.INVISIBLE);

### 方法二 ###