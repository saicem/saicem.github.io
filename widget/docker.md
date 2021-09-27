# docker

## 一篇很好的文档

[Docker-从入门到实践](https://yeasy.gitbook.io/docker_practice/)

## 常用又没那么常用的命令

- 删除虚悬镜像 `docker image prune`

## 温知识

- 其他 `docker build` [方法](https://yeasy.gitbook.io/docker_practice/image/build#qi-ta-docker-build-de-yong-fa)

## 容器不能访问外网

- 可能是这个设置的问题 `sysctl -w net.ipv4.ip_forward=1`
