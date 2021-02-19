---
title: mysql用户操作
date: 2020-12-27 14:55:01
updated: 2021-02-10 15:44:00
description:
category: mysql
---

### 安装

在 CentOS 8 上安装Mysql 需要使用 `dnf install @mysql`而不是 `dnf install mysql` 具体区别未知...

### 用户管理

```
CREATE USER <用户名> [ IDENTIFIED  BY] [ PASSWORD ] <口令>
CREATE USER 'jasmine'@'%' IDENTIFIED BY 'who is saicem';
drop user saicem;
```

1. <用户名>
指定创建用户账号，格式为 'user_name'@'host_name'。这里user_name是用户名，host_name为主机名，即用户连接 MySQL 时所在主机的名字。若在创建的过程中，只给出了账户的用户名，而没指定主机名，则主机名默认为“%”，表示一组主机。
2. PASSWORD
可选项，用于指定散列口令，即若使用明文设置口令，则需忽略PASSWORD关键字；若不想以明文设置口令，且知道 PASSWORD() 函数返回给密码的散列值，则可以在口令设置语句中指定此散列值，但需要加上关键字PASSWORD。
3. IDENTIFIED BY子句
用于指定用户账号对应的口令，若该用户账号无口令，则可省略此子句。
4. <口令>
指定用户账号的口令，在IDENTIFIED BY关键字或PASSWOED关键字之后。给定的口令值可以是只由字母和数字组成的明文，也可以是通过 PASSWORD() 函数得到的散列值。

### 权限管理
```
# 查看权限
SHOW GRANTS FOR user@host;
# 授予所有权限
GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost' WITH GRANT OPTION;
# 刷新权限
FLUSH PRIVILEGES;
```