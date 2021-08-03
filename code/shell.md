# shell

```shell
# 获取时间
"`date +%Y-%m-%dT%H:%M:%S`"
# 根据进程名杀死进程 需精确控制
`pkill` 
```

## win

- [oh my posh](https://ohmyposh.dev/)
> 配置文件在 `$Home \ [My] 文档 \ PowerShell \Profile.ps1`

### 临时设置终端代理

#### CMD
> 好像不可行

```
临时设置
set http_proxy=socks5://127.0.0.1:10808
set https_proxy=socks5://127.0.0.1:10808

如果有用户名和密码
set http_proxy_user=jake
set http_proxy_pass=abcd

取消设置
set http_proxy=
set https_proxy=
```

#### POWER SHELL
> 亲测可行
```
$env:https_proxy = "localhost:7890"
$env:http_proxy = "localhost:7890"
```

### 获取帮助
command /?

### net 命令
1. `net start` 查看已启动的服务
2. `net share` 查看当前用户下的共享目录
3. `net user` 查看当前机器上的用户

## zsh

- mac
- linux

### 改变用户默认shell

`/etc/passwd`

### bash 切换到 zsh 环境变量丢失

1. 在bash下面执行
`echo $PATH`
查看系统路径，复制路径。

2. 切换到zsh `sudo vim ~/.zshrc` 
在 If you come from bash you might have to change your $PATH.下面添加刚才的路径
`export PATH=" you path copy just now "`

3. `source ~/.zshrc` 加载配置

- [on my zsh安装脚本](https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)
> 配置文件在 .zshrc