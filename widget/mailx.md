## 安装`mailx`
```shell
yum  -y install mailx
```


## 编辑配置文件
```shell
vim /etc/mail.rc
```
```
set from=email@host             //发件人地址
set smtp=smtp.126.com           //smtp服务器地址
set smtp-auth-user=13510861001  //邮箱用户名
set smtp-auth-password="XXX"    //邮箱授权码&密码
set smtp-auth=login             //SMTP的认证方式，默认是login
```


## 发送邮件
- mail -s "subject" address < filepath
- echo "content" | mail -s "subject" address
- cat filepath | mail -s "subject" address
> mail mailx 均可

### 带附件
- `-a filepath`
> 该参数需要在 -s "subject" 之前


### 发送给多个收件人
- mail -s 'subject' xxx@139.com,xxx@163.com < filepath


## 运行过程
- 加参数 `-v` 在 `-s 'subject'`之前