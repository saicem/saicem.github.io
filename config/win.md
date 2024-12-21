# win

此文档用于重置`Windows`后快速配置环境。

## 系统设置

- 隐私和安全性 开发者选项
  - 开发人员模式
  - 显示文件扩展名
  - 显示隐藏和系统文件
- 剪切板➡开启历史记录
- Windows Search➡增强
- 语言与区域 微软拼音 键盘选项
  - 键盘选项 模式切换➡Shift
  - 常规 选择输入法默认模式➡英语

### Windows 安全中心

- 应用和浏览器控制
  - 检查应用和文件
  - 适用于 Microsoft Edge 的 SmartScreen

## Power Shell

```powershell
function Set-Proxy {
    $env:http_proxy = "http://127.0.0.1:7890"
    Write-Host -ForegroundColor Green "✨ proxy → on"
}

function Reset-Proxy {
    $env:http_proxy = ""
    Write-Host -ForegroundColor Green "✨ proxy → off"
}

Set-Alias spx Set-Proxy
Set-Alias rpx Reset-Proxy
```

## 软件

- [PowerToys](https://docs.microsoft.com/zh-cn/windows/powertoys/)【Win工具箱】
- [Office Tool Plus](https://otp.landian.vip/zh-cn/)【[KMS列表](https://www.coolhub.top/tech-articles/kms_list.html)】
- [Bandzip](http://www.bandisoft.com/)【6.25无广告】
- [7z](https://www.7-zip.org/)【图形界面无法处理编码问题】
- [draw.io](https://app.diagrams.net/)
- [WizTree](https://www.diskanalyzer.com/download) 【速度超快、存储占用分析】
- [Autoruns](https://learn.microsoft.com/en-us/sysinternals/downloads/autoruns) 【注册表清理工具，微软提供】
- [ContextMenuManager](https://gitee.com/BluePointLilac/ContextMenuManager/releases)【右键菜单管理】
- [Geek](https://geekuninstaller.com/) 【傻瓜式卸载软件】
- [Motrix](https://motrix.app/zh-CN/)【下载工具】
- [qBittorrent](https://www.qbittorrent.org/download)
- [Scrcpy](https://github.com/Genymobile/scrcpy/releases)【安卓投屏至电脑】
- [LocalSend](https://localsend.org)【开源、跨平台、局域网文件分享】
- [Syncthing](https://syncthing.net/)【开源、跨平台、局域网文件同步】

## 浏览器插件

- AdGuard
- Siphon
- DuckDuckGo
- 空白标签页
