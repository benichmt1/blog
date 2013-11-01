---
layout: post
title: "How to create a release signed apk file using Gradle?"
description: "How to create a release signed apk file using Gradle?"
category: android
tags: [gradle, android]
---
{% include JB/setup %}

From:
[http://stackoverflow.com/questions/18328730/how-to-create-a-release-signed-apk-file-using-gradle](http://stackoverflow.com/questions/18328730/how-to-create-a-release-signed-apk-file-using-gradle)

Gradle scripts can prompt for user input using the `System.console().readLine` method. The above code rewritten to use this will be:
<!-- more -->

{% highlight xml %} 
signingConfigs {
    release {
        storeFile file(System.console().readLine("\n\$ Enter keystore path: "))
        storePassword System.console().readLine("\n\$ Enter keystore password: ")
        keyAlias System.console().readLine("\n\$ Enter key alias: ")
        keyPassword System.console().readLine("\n\$ Enter key password: ")
    }
}
{% endhighlight %}
This will prompt for each of the parameters.

Having said this, in these situations, you are better off setting environment variables for these parameters and using them in the gradle file. Environment variables can be accessed with `System.getenv("<  VAR-NAME >")`

{% highlight xml %}
signingConfigs {
    release {
        storeFile file(System.getenv("KEYSTORE"))
        storePassword System.getenv("KEYSTORE_PASSWORD")
        keyAlias System.getenv("KEY_ALIAS")
        keyPassword System.getenv("KEY_PASSWORD")
    }
}
{% endhighlight %}
