---
layout: post
title: "[转载]反编译和回编译framework.jar"
description: "[转载]反编译和回编译framework.jar"
category: android
tags: [android]
---
{% include JB/setup %}

原文： [http://dss16694.iteye.com/blog/1436466](http://dss16694.iteye.com/blog/1436466)   

最近对android 2.3.3的framework.jar进行了一些反编译和回编译的操作，写下来备忘。
 
一、framework.jar反编译为smali文件
 
1、下载smali-1.2.6.jar和baksmali-1.2.6.jar这两个工具（下载地址：http://code.google.com/p/smali/downloads/list）
 <!-- more -->
 
2、将framework.jar中的classes.dex解压出来（好像不解压，直接用framework.jar也行）
 
3、使用baksmali.jar对classes.dex进行反编译（前提是安装了jdk，并且设置好了环境变量），执行命令：
 
java -jar baksmali-1.2.6.jar classes.dex -o out/
 
其中classes.dex是要反编译的文件，out/是要把反编译后的文件存放到的文件夹，如果不是在当前目录下，那么baksmali-1.2.6.jar还要加上路径
 
这样就OK了，在out文件夹中可以看到一堆扩展名为.smali的文件，用记事本就可以打开它们，从中可以窥到一些信息。但是与.java文件还是有一些不同，我也不太清楚这是什么结构。
 
二、smali文件回编译为classes.dex
 
1、一条命令就OK了：java -jar smali-1.2.6.jar out/ -o classes.dex
 
2、再把编译好的classes.dex放回到framework.jar中就行了（可以使用winrar、winzip之类的工具作为辅助）。
 
三、framework.jar反编译为.class和.java文件
 
1、下载以下工具：
 
（1）dex2jar（http://code.google.com/p/dex2jar/）
 
（2）xjad（http://www.skycn.com/soft/41898.html）或jd-gui（http://java.decompiler.free.fr/?q=jdgui）
 
2、使用dex2jar对framework.jar进行转换，执行命令：dex2jar.bat framework.jar   将会生成一个framework.jar.dex2jar.jar
 
3、直接对该jar文件解压，可以看到里面都是.class文件了
 
4、如果还需要转换成.java文件，可以使用xjad或jd-gui，均可将class文件变为java文件。
 
注：dex2jar工具也可以处理.dex文件，因此也可以不直接处理framework.jar。而是先将framework.jar解压，生成classes.dex后再处理也行。
