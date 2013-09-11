---
layout: post
title: "Canvas: trying to use a recycled bitmap android.graphics.Bitmap"
description: ""
category: android
tags: [android]
---
{% include JB/setup %}

问题：  
{% highlight java %}  
E/AndroidRuntime( 3281): java.lang.RuntimeException: Canvas: trying to use a recycled bitmap android.graphics.Bitmap@40561d70
E/AndroidRuntime( 3281):        at android.graphics.Canvas.throwIfRecycled(Canvas.java:955)
E/AndroidRuntime( 3281):        at android.graphics.Canvas.drawBitmap(Canvas.java:1044)
E/AndroidRuntime( 3281):        at android.graphics.drawable.BitmapDrawable.draw(BitmapDrawable.java:325)
E/AndroidRuntime( 3281):        at android.widget.ImageView.onDraw(ImageView.java:872)
E/AndroidRuntime( 3281):        at android.view.View.draw(View.java:7102)
E/AndroidRuntime( 3281):        at android.view.ViewGroup.drawChild(ViewGroup.java:1651)
E/AndroidRuntime( 3281):        at android.view.ViewGroup.dispatchDraw(ViewGroup.java:1375)
E/AndroidRuntime( 3281):        at android.view.View.draw(View.java:7105)
E/AndroidRuntime( 3281):        at android.support.v4.view.ViewPager.draw(ViewPager.java:1923)
E/AndroidRuntime( 3281):        at android.view.ViewGroup.drawChild(ViewGroup.java:1651)
E/AndroidRuntime( 3281):        at android.view.ViewGroup.dispatchDraw(ViewGroup.java:1375)
E/AndroidRuntime( 3281):        at android.view.View.draw(View.java:7105)
E/AndroidRuntime( 3281):        at android.view.ViewGroup.drawChild(ViewGroup.java:1651)
E/AndroidRuntime( 3281):        at android.view.ViewGroup.dispatchDraw(ViewGroup.java:1375)
E/AndroidRuntime( 3281):        at android.view.ViewGroup.drawChild(ViewGroup.java:1649)
E/AndroidRuntime( 3281):        at android.view.ViewGroup.dispatchDraw(ViewGroup.java:1375)
E/AndroidRuntime( 3281):        at android.view.View.draw(View.java:7105)
E/AndroidRuntime( 3281):        at android.widget.FrameLayout.draw(FrameLayout.java:357)
E/AndroidRuntime( 3281):        at com.android.internal.policy.impl.PhoneWindow$DecorView.draw(PhoneWindow.java:1988)
E/AndroidRuntime( 3281):        at android.view.ViewRoot.draw(ViewRoot.java:1547)
E/AndroidRuntime( 3281):        at android.view.ViewRoot.performTraversals(ViewRoot.java:1266)
E/AndroidRuntime( 3281):        at android.view.ViewRoot.handleMessage(ViewRoot.java:1898)
E/AndroidRuntime( 3281):        at android.os.Handler.dispatchMessage(Handler.java:99)
E/AndroidRuntime( 3281):        at android.os.Looper.loop(Looper.java:130)
E/AndroidRuntime( 3281):        at android.app.ActivityThread.main(ActivityThread.java:3768)
E/AndroidRuntime( 3281):        at java.lang.reflect.Method.invokeNative(Native Method)
E/AndroidRuntime( 3281):        at java.lang.reflect.Method.invoke(Method.java:507)
E/AndroidRuntime( 3281):        at com.android.internal.os.ZygoteInit$MethodAndArgsCaller.run(ZygoteInit.java:839)
E/AndroidRuntime( 3281):        at com.android.internal.os.ZygoteInit.main(ZygoteInit.java:597)
E/AndroidRuntime( 3281):        at dalvik.system.NativeStart.main(Native Method)
{% endhighlight %} 
<!-- more -->
原因：  
使用了已经被recycle回收过的无效Bitmap

解决办法：  
方法一：在创建和回收bitmap时，对bitmap设置同步锁；  
方法二：参考[http://bbs.csdn.net/topics/390196217](http://bbs.csdn.net/topics/390196217 ) （未验证）。