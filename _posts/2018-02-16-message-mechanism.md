---
title: windows中的消息机制
date: 2018-02-16 23:29:08
categories:
- art
tags:
- windows message
- event
---
消息机制指的事件驱动的机制，在WinForm和WebForm中，都是以事件驱动的。

## Windows中的消息
windows中的事件都是发送一个消息，windows有个消息队列服务可以查看。    
消息，就是指Windows发出的一个通知，告诉应用程序某个事情发生了。例如，单击鼠标、改变窗口尺寸、按下键盘上的一个键都会使Windows发送一个消息给应用程序。  
## .Net中的事件
.Net中事情的驱动都基于事件；  
一个是真实的物理事件，比如鼠标或者键盘按下放开了，时间到了等等。  
一个是对这些做了一次封装的事件，比如窗口最大化了，输入字符“A”了。  
这两个都是操作系统维护的，.net对他们又进行了一次封装，都集成到那些控件类的事件里去了，一般我们改不了，只能用。  
如果我们要自己定义事件，就要看到的是要做个什么事件，如果有硬件设备，那就从驱动做起，给操作系统发消息，一步步封装这个消息到你设计的类的事件里去。  
如果只是一个软件意义上的事件，那其实只是一种设计模式，一种观察者模式而已，只不过是在需要抛出事件的地方调用某个方法而已，java的事件就和.net很不一样，它只用接口而没有什么EVENT关键字，事实上，事件到底属不属于类都有争议，类有属性，有方法，但事件却不是类的固有属性，而只是方便写代码的一种语法。
## 硬件中的实现
事件都会放映到硬件的处理上。  
当用户点了鼠标，鼠标会收到一个信号，信号会被编码，通过总线传递给CPU，结果是引发CPU一个硬件中断。CPU收到中断请求会转到中断处理程序。中断处理程序是操作系统定义的，它的上层是驱动程序。驱动程序会解析硬件传来的参数，并且发给图形界面子系统，变成一条Windows消息投递给相关的窗体。我们的.NET Framework程序在下层不断接受Windows传来的消息，并且封装成一个事件调用，也就是填充合适的参数，比如鼠标位置信息等，然后调用事件。应用程序对应的事件处理程序被调用，实现对应的功能。