# Docker

## 容器内访问 localhost

host.docker.internal

## 设置安装 docker 的源

查看[清华大学开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn/help/docker-ce/)

## docker-compose 环境变量速记

- 变量可以加引号也可以不加，双引号内的文本会被转译
- Direct substitution
  - ${VAR} -> value of VAR
- Default value
  - ${VAR:-default} -> value of VAR if set and non-empty, otherwise default
  - ${VAR-default} -> value of VAR if set, otherwise default
- Required value
  - ${VAR:?error} -> value of VAR if set and non-empty, otherwise exit with error
  - ${VAR?error} -> value of VAR if set, otherwise exit with error
- Alternative value
  - ${VAR:+replacement} -> replacement if VAR is set and non-empty, otherwise empty
  - ${VAR+replacement} -> replacement if VAR is set, otherwise empty

## daemon.json

```json
{
    "registry-mirrors": [
        "https://mirror.ccs.tencentyun.com"
    ]
}
```

## 让 docker 可以从远程访问

不如直接看[文档](https://docs.docker.com/config/daemon/remote-access/)
