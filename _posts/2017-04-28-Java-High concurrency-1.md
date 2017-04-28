---
layout: post
title: "Java高并发之名词解释"
date: 2017-04-28 
description: "Java高并发之名词解释"
tag: JAVA 
---  

### 并发（Concurrency）和 并行（Parallelism）

<div align="center">
	<img src="/images/posts/java-concurrency/concurrency.jpg" height="300" width="500">  
</div>
　
	系统内只有一个CPU，而使用多进程或者多线程任务，那么真实环境中这些任务不可能是真实的并行的，毕竟一个CPU一次只能执行一条指令，这种情况下多进程或者多线程就是并发的，而不是并行的（操作系统会不停切换多个任务）。真实的并行也只能出现在拥有多个CPU的系统中（如 多核CPU）。

### 阻塞（Blocking）和 非阻塞（Non-Blocking）　

	系统内只有一个CPU，而使用多进程或者多线程任务，那么真实环境中这些任务不可能是真实的并行的，毕竟一个CPU一次只能执行一条指令，这种情况下多进程或者多线程就是并发的，而不是并行的（操作系统会不停切换多个任务）。真实的并行也只能出现在拥有多个CPU的系统中（如 多核CPU）。


转载请注明原地址，朱肖磊的博客：[http://zhuxiaolei.github.io](http://zhuxiaolei.github.io) 谢谢！