# ssh

## 在一台电脑上，如何配置多个SSH Key

```text
Host alias
    HostName hostname
    User user
    IdentityFile ~/.ssh/key
```

`Host` 指定别名，在本机可以替代使用。`HostName` `User` 为实际主机和用户。
在有多个 key 的情况下配置区分连接使用的 key。
