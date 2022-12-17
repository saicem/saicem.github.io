# win

此文档用于重置`Windows`后快速配置环境。

## 系统设置

- 显示文件后缀名
- 显示隐藏文件
- 剪切板➡开启历史记录
- 搜索➡增强
- 输入法默认模式➡英文
- 电源和睡眠➡其他电源设置➡启用快速启动（推荐）关闭
- 回收站隐藏➡主题➡桌面图标设置
- 系统保护➡系统还原➡设置还原点

> 睡眠和休眠
>
> - 睡眠还保持着开机状态的，休眠是关机了，但是再次开机之后和关闭时的系统状态是一样的
> - 睡眠还是保持着系统运行数据在内存中，而休眠则将内存中的数据保存在硬盘中（应该是虚拟内存）
> - 睡眠的唤醒时间应该比休眠要短

## Power Shell

```powershell
Import-Module posh-git
Import-Module oh-my-posh
Set-PoshPrompt -Theme robbyrussel

function Set-Proxy {
    param(
        $Name = "terminal"
    )

    if ($Name -eq "terminal") {
        $env:https_proxy = "http://127.0.0.1:7981"
        $env:http_proxy = "http://127.0.0.1:7981"
        $env:all_proxy = "socks5://127.0.0.1:7980"
        Write-Host -ForegroundColor Green "✨ proxy ⇒ on"
    }
}

function Reset-Proxy {
    param(
        $Name = "terminal"
    )

    if ($Name -eq "terminal") {
        $env:https_proxy = ""
        $env:http_proxy = ""
        $env:all_proxy = ""
        Write-Host -ForegroundColor Green "✨ proxy ⇒ off"
    }
}

Set-Alias spx Set-Proxy
Set-Alias rpx Reset-Proxy
```

## 软件

- [PowerToys](https://docs.microsoft.com/zh-cn/windows/powertoys/)
- [office tool plus](https://otp.landian.vip/zh-cn/)【装office很方便】
- [Captura](https://github.com/MathewSachin/Captura)
- [Coodesker](https://www.coodesker.com/)【在[Github](https://github.com/coodesker/coodesker-desktop)上，但并不开源】
- [Bandzip](http://www.bandisoft.com/)
- [7z](https://www.7-zip.org/)
- [ApiFox](https://www.apifox.cn/)
- [WinSCP](https://winscp.net/eng/docs/lang:chs)
- [DBeaver](https://dbeaver.io/)
- [BloomRpc](https://github.com/bloomrpc/bloomrpc)
- [V2rayN](https://github.com/2dust/v2rayN/releases)
- [geek](https://geekuninstaller.com/) 【傻瓜式卸载软件】
- [WizTree](https://www.diskanalyzer.com/download) 【速度超快】
- [Autoruns](https://learn.microsoft.com/en-us/sysinternals/downloads/autoruns) 【注册表清理工具，微软提供】
- [PotPlayer](https://potplayer.daum.net/?lang=zh_CN)
- [draw.io](https://app.diagrams.net/)
- [HTTPie](https://httpie.io/)
- [EarTrumpet](https://eartrumpet.app/)【电脑音频管理】

## 浏览器插件

- Adblock plus
- Tampermonkey
- 草料二维码 【方便的在电脑处理二维码】
- Vimium C
- iTab【漂亮的浏览器起始页】
- uBlacklist 【拒绝内容农场】
