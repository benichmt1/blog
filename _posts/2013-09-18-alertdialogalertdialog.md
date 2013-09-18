---
layout: post
title: "关于AlertDialog弹出后，触摸其它区域AlertDialog消失的解决方法"
description: ""
category: android
tags: [android]
---
{% include JB/setup %}

在AlertDialog.Builder.create()之后才能调用这两个方法。

方法一：

setCanceledOnTouchOutside(false);调用这个方法时，按对话框以外的地方不起作用。按返回键起作用
<!-- more -->

方法二：

setCanceleable(false);调用这个方法时，按对话框以外的地方不起作用。按返回键也不起作用