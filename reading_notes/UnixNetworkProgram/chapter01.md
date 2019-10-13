# 简介

> yangliang@20161001



## 网络编程概述
编写计算机网络通信程序，首先需要确定这些程序互相通信所用的 `协议(protocol)`

网络通信有多个层次，这个一般遵循 `OSI模型`。各个层次都有对应的协议，且都是独立的，例如客户和服务器之间使用某个应用协议通信，传输层却使用TCP通信。


### OSI模型

截图展示



## 一个简单的Demo
通过demo了解网络编程的client和server端的基本编写方法，基本概念及常用API。这些在第四章有详细介绍。

client

* socket
* connect

server

* bind
* listen
* accept



## 其他

### 多客户请求处理
一个服务器同时处理多个客户端请求的问题，有多种方法如下

* 多进程：fork
* 多线程
* select？


### 包裹函数
书中对要调用的大多数系统函数定义了个字的包裹函数，实际就是一层封装。使用这些包裹函数来检查错误，输出适当的消息，以及字出错时终止程序的运行。


### 问题
* Q: why套接字提供的是从OSI模型的顶上三层进入传输层的接口
* A: 
	* `网络应用` 和 `通信细节` 的隔离: 顶上三层处理具体网络应用(如FTP、Telnet、HTTP)；底下四层对网络应用了解不多，却处理所有的通讯细节，例如发送数据、等待确认、给无序到达的数据排序、计算并验证校验和
	* `用户进程` 和 `系统内核` 的独立: 顶上三层通常构成所谓的 `用户进程`；底下四层却通常作为操作系统内核的一部分提供



## 小结
主要的焦点: 如何使用套接字编写使用TCP或UDP的网络应用程序。