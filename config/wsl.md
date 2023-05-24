# Windows Sub Linux

## 配置

```zsh
export TZ='Asia/Shanghai'

host_ip=$(cat /etc/resolv.conf |grep "nameserver" |cut -f 2 -d " ")
spx() {
    export ALL_PROXY="http://$host_ip:7890"
    echo ✨ proxy → on
}
rpx() {
    unset ALL_PROXY
    echo ✨ proxy → off
}

```
