+++
title = 'HTTP 各版本原理及演变过程'
date = 2025-04-01T21:51:10+08:00
draft = true

[cover]
hiddenInList = false
image = './posts/HTTP 各版本原理及演变过程/images/HTTP%20演变过程.png'
+++

## 什么是 HTTP？

当你通过浏览器游荡在各式各样的网页时，你是否会疑惑这些网页是通过怎样的方式在互联网上传播的？那么我的朋友，你可能需要了解一下 HTTP。
超文本传输协议（英语：HyperText Transfer Protocol，缩写：HTTP）是一种用于分布式、协作式和超媒体信息系统的应用层协议。HTTP是万维网的数据通信的基础。设计 HTTP 的最初目的就是提供一种发布和接收 HTML 页面的方法。

> OSI 将计算机网络体系结构划分为七层：应用层、表现层、会话层、传输层、网络层、数据链路层、物理层。
> 实际应用中使用的是 TCP/IP 的四层结构：应用层、传输层、网络层、数据链路层。

## HTTP 的演变过程

![HTTP 演变过程](./images/HTTP%20演变过程.png)

### HTTP/0.9



### HTTP/1.0

HTTP/1.0 基于 TCP 实现，对同一服务器的每个请求都需要单独的 TCP 连接。

![HTTP/1 请求流程](./images/HTTP%201%20请求流程.png)

让我们来看看具体的请求报文和响应报文信息。
请求报文由四部分组成：请求行，请求头，空行，消息体

### HTTP/1.1

HTTP/1.1 引入 keep-alive 机制，单个连接可以被重复用于多个请求。
因为客户端不需要为每个请求建立 TCP 连接， 持久连接减少了过去多个请求情况下的请求延迟。

![HTTP/1.1 keep-alive 机制](./images/HTTP%201.1%20keep-alive%20机制.png)

> **（浏览器不再支持）** HTTP/1.1 还引入 pipelining 功能，允许客户端在等待响应之前发送多个请求，响应必须按照与请求相同的顺序接收。但是该功能存在队头阻塞的问题，因为同一连接上的后续请求必须等待前面的请求完成，如果请求由于数据包丢失等原因被阻止，则同一连接上的所有后续请求也会受到影响。



### HTTP/2

### HTTP/3