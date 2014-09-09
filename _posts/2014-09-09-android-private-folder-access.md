---
layout: post
title: "[转载]android私有文件夹的访问"
description: "android私有文件夹的访问"
category: android
tags: [android]
---
{% include JB/setup %}

原文：[http://www.cnblogs.com/viki117/archive/2010/09/27/1837091.html](http://www.cnblogs.com/viki117/archive/2010/09/27/1837091.html)

首先内部存储路径为/data/data/youPackageName/，下面讲解的各路径都是基于你自己的应用的内部存储路径下。所有内部存储中保存的文件在用户卸载应用的时候会被删除。

一、 files 

1. Context.getFilesDir()，该方法返回/data/data/youPackageName/files的File对象。
1. Context.openFileInput()与Context.openFileOutput()，只能读取和写入files下的文件，返回的是FileInputStream和FileOutputStream对象。
1. Context.fileList()，返回files下所有的文件名，返回的是String[]对象。
1. Context.deleteFile(String)，删除files下指定名称的文件。

二、cache

Context.getCacheDir()，该方法返回/data/data/youPackageName/cache的File对象。

三、custom dir

getDir(String name, int mode)，返回/data/data/youPackageName/下的指定名称的文件夹File对象，如果该文件夹不存在则用指定名称创建一个新的文件夹。