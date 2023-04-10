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

## Power Shell

```powershell
function Set-Proxy {
    $env:https_proxy = "http://127.0.0.1:7890"
    $env:http_proxy = "http://127.0.0.1:7890"
    Write-Host -ForegroundColor Green "✨ proxy ⇒ on"
}

function Reset-Proxy {
    $env:https_proxy = ""
    $env:http_proxy = ""
    Write-Host -ForegroundColor Green "✨ proxy ⇒ off"
}

Set-Alias spx Set-Proxy
Set-Alias rpx Reset-Proxy
```

## 软件

- [PowerToys](https://docs.microsoft.com/zh-cn/windows/powertoys/)【Win工具箱】
- [office tool plus](https://otp.landian.vip/zh-cn/)【装office很方便】
- [Captura](https://github.com/MathewSachin/Captura)【录屏】
- [Coodesker](https://www.coodesker.com/)【在[Github](https://github.com/coodesker/coodesker-desktop)上，但并不开源】
- [Bandzip](http://www.bandisoft.com/)【6.25无广告】
- [7z](https://www.7-zip.org/)【图形界面无法处理编码问题】
- [ApiFox](https://www.apifox.cn/)
- [WinSCP](https://winscp.net/eng/docs/lang:chs)
- [DBeaver](https://dbeaver.io/)【开源的数据库管理】
- [BloomRpc](https://github.com/bloomrpc/bloomrpc)
- [V2rayN](https://github.com/2dust/v2rayN/releases)
- [PotPlayer](https://potplayer.daum.net/?lang=zh_CN)
- [draw.io](https://app.diagrams.net/)
- [HTTPie](https://httpie.io/)【代替 Postman】
- [EarTrumpet](https://eartrumpet.app/)【电脑音频管理，当你有多个发出声音的设备的时候】
- [geek](https://geekuninstaller.com/) 【傻瓜式卸载软件】
- [WizTree](https://www.diskanalyzer.com/download) 【速度超快】
- [Autoruns](https://learn.microsoft.com/en-us/sysinternals/downloads/autoruns) 【注册表清理工具，微软提供】
- [ContextMenuManager](https://gitee.com/BluePointLilac/ContextMenuManager/releases)【上下文菜单管理】

## 编程环境

### 换源

```pwsh
npm config set registry https://registry.npm.taobao.org
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```
