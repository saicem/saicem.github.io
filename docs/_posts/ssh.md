---
title: ssh
date: 2021-02-09 16:03:10
updated: 2021-02-09 16:03:10
description:
category: 编程
---
生成ssh公钥
`
ssh-keygen -t rsa
`
将生产的 id_rsa.pub 的内容复制至linux上的 ~/.ssh/authorized_keys 即可实现免密登录