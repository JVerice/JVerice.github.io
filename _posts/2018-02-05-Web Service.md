---
layout: post
title:  "Web Service"
date:   2018-02-05 10:52:09
categories: Java WebService
tags: WebService WSDL SQAP
author: JVerice
---

* content
{:toc}

> Web Service 使用




## Web Service 

> Web Services 可使您的应用程序成为 Web 应用程序。
Web Services 通过 Web 进行发布、查找和使用。


*什么是Web Services？

    Web Services 是应用程序组件
    Web Services 使用开放协议进行通信
    Web Services 是独立的（self-contained）并可自我描述
    Web Services 可通过使用UDDI来发现
    Web Services 可被其他应用程序使用
    XML是 Web Services 的基础



* Web services 平台的元素：

    - SOAP (简易对象访问协议)
    - UDDI (通用描述、发现及整合)
    - WSDL (Web services 描述语言)

* 它如何工作？

    基础的 Web Services 平台是 XML + HTTP。
HTTP 协议是最常用的因特网协议。
XML 提供了一种可用于不同的平台和编程语言之间的语言。

* Web Services 可以将应用程序转换为网络应用程序。

    通过使用 Web Services，您的应用程序可以向全世界发布信息，或提供某项功能。

* Web Services 可以被其他应用程序使用。

    通过 Web Services，您的会计部门的 Win 2k 服务器可以与 IT 供应商的 UNIX 服务器相连接。

* 基本的 Web Services 平台是 XML+HTTP。

    Web services 使用 XML 来编解码数据，并使用 SOAP 来传输数据。
  
## UDDI
UDDI 是一种目录服务，通过它，企业可注册并搜索 Web services。
* UDDI 指通用的描述、发现以及整合（Universal Description, Discovery and Integration）。
* UDDI 是一种用于存储有关 web services 的信息的目录。
* UDDI 是一种由 WSDL 描述的网络服务接口目录。
* UDDI 经由 SOAP 进行通迅。
* UDDI 被构建于 Microsoft .NET 平台之中。

## WSDL

WSDL 是基于 XML 的用于描述 Web Services 以及如何访问 Web Services 的语言。w3school查看文档及教程
* WSDL 指网络服务描述语言
* WSDL 使用 XML 编写
* WSDL 是一种 XML 文档
* WSDL 用于描述网络服务
* WSDL 也可用于定位网络服务
* WSDL 还不是 W3C 标准

## SOAP

基本的 Web services 平台是 XML + HTTP。

SOAP 是基于 XML 的简易协议，可使应用程序在 HTTP 之上进行信息交换。
或者更简单地说：SOAP是用于访问网络服务的协议。
* SOAP 指简易对象访问协议
* SOAP 是一种通信协议
* SOAP 用于应用程序之间的通信
* SOAP 是一种用于发送消息的格式
* SOAP 被设计用来通过因特网进行通信
* SOAP 独立于平台
* SOAP 独立于语言
* SOAP 基于 XML
* SOAP 很简单并可扩展
* SOAP 允许您绕过防火墙
* SOAP 将作为 W3C 标准来发展
 
语法规则：

* SOAP 消息必须用 XML 来编码
* SOAP 消息必须使用 SOAP Envelope 命名空间
* SOAP 消息必须使用 SOAP Encoding 命名空间
* SOAP 消息不能包含 DTD 引用
* SOAP 消息不能包含 XML 处理指令

SOAP消息基本结构：

```
<?xml version="1.0"?>
<soap:Envelope
xmlns:soap="http://www.w3.org/2001/12/soap-envelope"
soap:encodingStyle="http://www.w3.org/2001/12/soap-encoding">

<soap:Header>
  ...
  ...
</soap:Header>

<soap:Body>
  ...
  ...
  <soap:Fault>
    ...
    ...
  </soap:Fault>
</soap:Body>

</soap:Envelope>

```
实例：

SOAP请求
```
POST /InStock HTTP/1.1
Host: www.example.org
Content-Type: application/soap+xml; charset=utf-8
Content-Length: nnn

<?xml version="1.0"?>
<soap:Envelope
xmlns:soap="http://www.w3.org/2001/12/soap-envelope"
soap:encodingStyle="http://www.w3.org/2001/12/soap-encoding">

  <soap:Body xmlns:m="http://www.example.org/stock">
    <m:GetStockPrice>
      <m:StockName>IBM</m:StockName>
    </m:GetStockPrice>
  </soap:Body>
  
</soap:Envelope>
```
SOAP响应
```
HTTP/1.1 200 OK
Content-Type: application/soap+xml; charset=utf-8
Content-Length: nnn

<?xml version="1.0"?>
<soap:Envelope
xmlns:soap="http://www.w3.org/2001/12/soap-envelope"
soap:encodingStyle="http://www.w3.org/2001/12/soap-encoding">

  <soap:Body xmlns:m="http://www.example.org/stock">
    <m:GetStockPriceResponse>
      <m:Price>34.5</m:Price>
    </m:GetStockPriceResponse>
  </soap:Body>
  
</soap:Envelope>
```
