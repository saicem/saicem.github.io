# shell

## win

- [oh my posh](https://ohmyposh.dev/)

> 配置文件在 `$Home \ [My] 文档 \ PowerShell \Profile.ps1`

### 临时设置终端代理

#### POWER SHELL

```bash
$env:https_proxy = "localhost:7890"
$env:http_proxy = "localhost:7890"
```

### 获取帮助

command /?

### net 命令

1. `net start` 查看已启动的服务
2. `net share` 查看当前用户下的共享目录
3. `net user` 查看当前机器上的用户
