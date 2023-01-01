# 自签证书

## 生成私钥

```bash
openssl genrsa -out server.key 1024
```

## 生成证书请求文件

```bash
openssl req -new -key server.key -out server.csr
```

必须包含的内容

```text
O = Internet Widgits Pty Ltd
S = Some-State
C = AU
```

## 根据私钥和请求文件生成证书

```bash
openssl x509 -req -in server.csr -out server.crt -signkey server.key
```

## 根证书签发

```bash
openssl x509 -req -CA ca.crt -CAkey ca.key -CAcreateserial -in server.csr -out server.crt
```

## expecting: TRUSTED CERTIFICATE

在 `openssl` 命令中添加 `-trustout`，见 [stackoverflow](https://stackoverflow.com/questions/51899844/nginx-ssl-no-start-line-expecting-trusted-certificate)
