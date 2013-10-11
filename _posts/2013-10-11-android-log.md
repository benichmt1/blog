---
layout: post
title: "android log"
description: "android log"
category: android
tags: [github,android]
---
{% include JB/setup %}

#android-log

##Introduction
android lib - log

##Download
Download [the latest jar][1] or grab via Maven:

{% highlight xml %}
<dependency>
  <groupId>com.github.snowdream.android.util</groupId>
  <artifactId>log</artifactId>
  <version>0.0.4</version>
</dependency>
{% endhighlight %}
<!-- more -->

##Usage
1、enable/disable log  
{% highlight java %}
Log.setEnabled(true);  
Log.setEnabled(false);  
{% endhighlight %}

2、set the Tag for the log  
{% highlight java %}
Log.setTag("Android");  
{% endhighlight %}

3、log simple  
{% highlight java %}
Log.d("test");  
Log.v("test");  
Log.i("test");  
Log.w("test");  
Log.e("test");  
{% endhighlight %}

4、log simple -- set custom tag  
{% highlight java %}
Log.d("TAG","test");  
Log.v("TAG","test");  
Log.i("TAG","test");  
Log.w("TAG","test");  
Log.e("TAG","test");  
{% endhighlight %}

5、log advance  
{% highlight java %}
Log.d("test",new Throwable("test"));  
Log.v("test",new Throwable("test"));  
Log.i("test",new Throwable("test"));  
Log.w("test",new Throwable("test"));  
Log.e("test",new Throwable("test"));  
{% endhighlight %}

6、log advance  -- set custom tag   
{% highlight java %}
Log.d("TAG","test",new Throwable("test"));  
Log.v("TAG","test",new Throwable("test"));  
Log.i("TAG","test",new Throwable("test"));  
Log.w("TAG","test",new Throwable("test"));  
Log.e("TAG","test",new Throwable("test"));  
{% endhighlight %}

##License
{% highlight xml %} 
 Copyright (C) 2013 Snowdream Mobile
  
 Licensed under the Apache License, Version 2.0 (the "License");
 you may not use this file except in compliance with the License.
 You may obtain a copy of the License at
  
 http://www.apache.org/licenses/LICENSE-2.0
  
 Unless required by applicable law or agreed to in writing, software
 distributed under the License is distributed on an "AS IS" BASIS,
 WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 See the License for the specific language governing permissions and
 limitations under the License.
{% endhighlight %}

[1]:https://oss.sonatype.org/content/groups/public/com/github/snowdream/android/util/log/0.0.4/log-0.0.4.jar