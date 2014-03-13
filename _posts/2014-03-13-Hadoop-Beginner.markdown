---
layout: post
title: "Hadoop Beginner --- How to compile Hadoop Application"
date: 2014-03-13 23:47:23
categories: Hadoop java
---

As a Hadoop freshman, as fresh as one night of playing, tried to compile and get some Hello World application to work. The code I get are from [Hadoop: The Definitive Guide](http://hadoopbook.com/) as the tutorial code of this cook book.  
For the charpter 2 code, all-night testing still could not get the cpp code into work. For the java code, I finally successfully compile and it by:  
``javac -classpath `hadoop classpath` your/main/java/file.java``  
And run it by:  
``export HADOOP_CLASSPATH=your/built/class/path/ && hadoop yourJavaClass``

