---
title: Windows 平台脚本的演变
date: 2018-01-15 23:29:08
categories:
- art
tags:
- cmd
- powershell
- script
---
脚本语言是解释性语言，一般不需要编译就可解释执行，一般是命令式的。

## 早期16位时的command（Batch）
早期的Dos系统和16位的windows系统，用command进行脚本编程，有一套内部的方法，脚本后缀是bat。

## 32位时的cmd
cmd对之前的bat进行了扩展，扩展了一下方法和函数。

## 进阶的WScript和CScript
用js和vbs解析器对脚本进行扩展，可以使用js和vbs语言写脚本。

## 面向对象的Powershell
powershell使用面向对象的方法，传输的是对象，可以应用.net framwork。

## 其它脚本和运行环境
很多平台也需要做一些操作，但是不需要用重量级语言那么复杂。这就需要一些脚本。

## Chrome插件
利用html和js，简单的配置，就可以制作插件。

## Bash脚本
linux操作系统级脚本

## 小结
脚本语言（Script languages）原本是为了缩短编写-编译-连接-运行过程而创建的计算机编程语言。  
很多脚本语言实际上已经超过简单的用户命令序列的指令，还可以编写更复杂的程序。