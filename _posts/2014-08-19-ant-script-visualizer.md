---
layout: post
title: "Ant Script Visualizer"
description: "Ant Script Visualizer"
category: ant
tags: [ant]
---
{% include JB/setup %}

##Ant Script Visualizer
* [ant2dot][1] - using GraphViz toolkit to generate the final graph;
* [Vizant][2] - using GraphViz toolkit to generate the final graph;
* [Grand][3] - using GraphViz toolkit to generate the final graph;
* [ant-script-visualizer][4] - using GraphViz toolkit to generate the final graph.
* [NAntGraph][5] - using GraphViz toolkit to generate the final graph.
* [ant-dependency-viewer][6] - using GraphViz toolkit to generate the final graph.
<!-- more -->  

##NAntGraph
It is the recommend ant script visualizer on windows.       

1. Graphviz - Graph Visualization Software      
Download **[graphviz-2.38.msi](http://www.graphviz.org/pub/graphviz/stable/windows/graphviz-2.38.msi)** and install it.      
Then add it's subdir `bin` into the environment variables in windows.    


2. NAntGraph       
Download **[NAntGraph2](http://www.nichesoftware.co.nz/downloads/NAntGraph-2.2.zip)** and extract it.     
Look at the article    [http://www.nichesoftware.co.nz/2010/06/30/nantgraph-configuration.html](http://www.nichesoftware.co.nz/2010/06/30/nantgraph-configuration.html),     maybe you will need configure it.

3. Run with build.xml  
Open the cmd console windows, Run as follows:  
 {% highlight java %}
D:\bin\NAntGraph-2.2>NAntGraph2.exe -buildFile="D:\android-sdk-windows\sdk\tools\ant\build.xml"
Loading D:\android-sdk-windows\sdk\tools\ant\build.xml
Generating Graph
Saving graph image to D:\android-sdk-windows\sdk\tools\ant\build.png
{% endhighlight %}  


**Preview :**
![build.png]({{ BASE_PATH }}/assets/images/build.png)

**Usage :**
<pre>
D:\bin\NAntGraph-2.2>NAntGraph2.exe --help
      --out=VALUE
      --help, -?
      --buildFile, -b=VALUE
      --descriptions
      --dotscript[=VALUE]
      --font[=VALUE]
      --fontsize[=VALUE]
</pre>

##Reference
1. [http://stackoverflow.com/a/12388153](http://stackoverflow.com/a/12388153)
2. [http://www.javaranch.com/journal/200711/ant_dependency_graph.html](http://www.javaranch.com/journal/200711/ant_dependency_graph.html)
3. [http://www.nichesoftware.co.nz/2010/06/30/nantgraph-configuration.html](http://www.nichesoftware.co.nz/2010/06/30/nantgraph-configuration.html)
4. [http://www.graphviz.org/Download_windows.php](http://www.graphviz.org/Download_windows.php)

[1]: http://ant2dot.sourceforge.net/#what
[2]: http://vizant.sourceforge.net/
[3]: http://www.ggtools.net/grand/
[4]: http://code.google.com/p/ant-script-visualizer/ 
[5]: http://www.nichesoftware.co.nz/nantgraph.html
[6]: https://github.com/ajsquared/ant-dependency-viewer