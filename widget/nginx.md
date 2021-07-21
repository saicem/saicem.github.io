---
title: Nginx配置<br>
date: 2021-02-23 20:48:08
---

## uri中的变量

```nginx
$args #这个变量等于请求行中的参数。
$content_length #请求头中的Content-length字段。
$content_type #请求头中的Content-Type字段。
$document_root #当前请求在root指令中指定的值。
$host #请求主机头字段，否则为服务器名称。
$http_user_agent #客户端agent信息
$http_cookie #客户端cookie信息
$limit_rate #这个变量可以限制连接速率。
$request_body_file #客户端请求主体信息的临时文件名。
$request_method #客户端请求的动作，通常为GET或POST。
$remote_addr #客户端的IP地址。
$remote_port #客户端的端口。
$remote_user #已经经过Auth Basic Module验证的用户名。
$request_filename #当前请求的文件路径，由root或alias指令与URI请求生成。
$query_string #与args相同。
$scheme #HTTP方法（如http，https）。
$server_protocol #请求使用的协议，通常是HTTP/1.0或HTTP/1.1。
$server_addr #服务器地址，在完成一次系统调用后可以确定这个值。
$server_name #服务器名称。
$server_port #请求到达服务器的端口号。
$request_uri #包含请求参数的原始URI，不包含主机名，如：”/foo/bar.php?arg=baz”。
$uri #不带请求参数的当前URI，uri不包含主机名，如”/foo/bar.html”。
$document_uri #与$uri相同。
```

## Core functionality

[参考链接](http://nginx.org/en/docs/ngx_core_module.html)

## Configuring HTTPS servers

[参考链接](https://cloud.tencent.com/developer/section/1258927)

## How nginx processes a request

[参考链接](https://cloud.tencent.com/developer/section/1258933)

## 一些小问题

{% note green %}
listen 443 与 listen 443 ssl 的区别?
{% endnote %}

{% note blue %}
只要配置了证书，都可以通过https访问。但没有ssl的话，可以直接通过443端口访问，而设置了ssl则会返回。
```html
<html>
<head><title>400 The plain HTTP request was sent to HTTPS port</title></head>
<body bgcolor="white">
<center><h1>400 Bad Request</h1></center>
<center>The plain HTTP request was sent to HTTPS port</center>
<hr><center>nginx/1.14.1</center>
</body>
</html>
```
{% endnote %}