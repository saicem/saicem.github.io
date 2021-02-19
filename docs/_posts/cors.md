---
title: CORS问题
date: 2020-12-19 16:44:54
updated: 2020-12-19 16:44:54
category: CORS
---
想使用api但网页有这个CORS

C#后端参考
[(CORS) 启用跨域请求 ASP.NET Core](https://docs.microsoft.com/zh-cn/aspnet/core/security/cors?view=aspnetcore-5.0)

>说是要设置什么 Access-Control-Allow-Origin 请求头 其实是服务端的请求头 搞得我以为是客户端的 忙活半天。

nginx 记得设置ssl

ajax请求记得使用https
[XMLHttpRequest](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest)
[跨源资源共享（CORS）](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Access_control_CORS)
[Access-Control-Allow-Origin](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/Access-Control-Allow-Origin)