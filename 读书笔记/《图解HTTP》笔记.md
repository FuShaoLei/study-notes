# 《图解HTTP》笔记

## 第一章 了解web及网络基础

互联网是再TCP/IP协议族的基础上运作起来的

TCP/IP协议族分为四层：

- 应用层：决定了向用户提供应用服务时的通信活动，如FTP，DNS，HTTP等
- 传输层：提供数据传输，如TCP，UDP
- 网络层：处理数据包？
- 链路层：用来处理连接网路的硬件部分

与HTTP密切相关的几个协议：

- IP协议：作用是保证数据包传送到指定目标
- TCP协议：作用是可靠传输
- DNS服务：负责解析域名成IP地址

URI和URL

- URI是统一资源标识符，强调是唯一标识
- URL是统一资源定位符，强调的是位置，在什么位置上

## 第二章 简单的HTTP协议

请求访问资源的一端为客户端，提供资源的一端为服务器端，始终都是由客户端来建立通信的

客户端请求报文：

```java
//  方法  URI     版本协议
    GET /user/   HTTP/1.1
// Request Headers   
    Host: api.github.com
    Content-Type: text/plain
    Content-Length:21
// Request Body
    name=fushaolei&age=21
```

服务端响应报文：

```java
//  版本协议    状态码 
	HTTP/1.1  200   OK
// Response Headers        
    Content-Type: application/json
    Content-Length:21
// Response Body
    bodybodybodybodybodybodybodybodybodybodybodybodybodybodybodybodybodybodybodybody
```

Http是不保存状态的协议

各种请求方法：

| 方法    | 说明                                                         |
| ------- | ------------------------------------------------------------ |
| GET     | 请求资源，无Request Body，有Response Body                    |
| POST    | 用于增加或修改资源，有Request Body，有Response Body          |
| PUT     | 同样用于增加或修改资源，但和POST不同的是，PUT是幂等的（调用一次与连续调用多次是等价的），有Response Body |
| HEAD    | 获得报文首部，没有Response Body                              |
| DELETE  | 删除文件                                                     |
| OPTIONS | 询问支持方法                                                 |
| TRACE   | 追踪路径，可以查询发出去的请求是被怎样加工修改的             |
| CONNECT | 要求用隧道协议连接代理                                       |

使用Cookie进行状态管理，客户端保存好服务器端发送过来的Set-Cookie字段，在每次请求的时候带上Cookie，从而验证身份

## 第三章 HTTP报文内的HTTP信息

Http报文本质是由多行（CR+LF换行符）数据构成的**字符串文本**

请求报文：

```java
请求行
各种首部字段
// 换行，就这里空一行
Request body（如果有的话）
```

响应报文：

```java
状态行
各种首部字段
// 换行，就这里空一行
Response body（如果有的话）
```

首部字段有4种，分别是，通用首部，请求首部，响应首部，实体首部