# win

此文档用于重置`Windows`后快速配置环境。

## 系统设置

- 隐私和安全性 开发者选项
  - 开发人员模式
  - 显示文件扩展名
  - 显示隐藏和系统文件
  - 终端 Windows 终端
- 剪切板➡开启历史记录
- Windows Search➡增强
- 个性化 文本输入 更多设置 候选字词窗口 候选词数
- 语言与区域 微软拼音 键盘选项
  - 键盘选项 模式切换➡Shift
  - 常规 选择输入法默认模式➡英语
- 电源和睡眠➡其他电源设置➡启用快速启动（推荐）关闭
- 回收站隐藏➡主题➡桌面图标设置
- 系统保护➡系统还原➡设置还原点

### Windows 安全中心

- 应用和浏览器控制
  - 检查应用和文件
  - 适用于 Microsoft Edge 的 SmartScreen

## Power Shell

```powershell
function Set-Proxy {
    $env:https_proxy = "http://127.0.0.1:7890"
    $env:http_proxy = "http://127.0.0.1:7890"
    $env:all_proxy = "socks5://127.0.0.1:7891"
    Write-Host -ForegroundColor Green "✨ proxy → on"
}

function Reset-Proxy {
    $env:https_proxy = ""
    $env:http_proxy = ""
    $env:all_proxy = ""
    Write-Host -ForegroundColor Green "✨ proxy → off"
}

Set-Alias spx Set-Proxy
Set-Alias rpx Reset-Proxy


# https://ohmyposh.dev/docs/themes
# https://www.nerdfonts.com/font-downloads 'CaskaydiaCove Nerd Font'
# oh-my-posh init pwsh | Invoke-Expression
# material
oh-my-posh init pwsh --config 'C:\Users\saicem\AppData\Local\Programs\oh-my-posh\themes\material.omp.json' | Invoke-Expression

# 设置自己的命令行提示
# function prompt {
#     # "PS $($executionContext.SessionState.Path.CurrentLocation)$('>' * ($nestedPromptLevel + 1)) ";
#     # 🥵🥶👻🦄🐇❗❓⁉️☢️☣️⚠️
#     "`e[34m$env:UserName`e[0m ";
# }
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
- [PotPlayer](https://potplayer.daum.net/?lang=zh_CN)
- [V2rayN](https://github.com/2dust/v2rayN/releases)
- [Clash for Windows](https://github.com/Fndroid/clash_for_windows_pkg/releases)
- [draw.io](https://app.diagrams.net/)
- [HTTPie](https://httpie.io/)【代替 Postman】
- [EarTrumpet](https://eartrumpet.app/)【电脑音频管理，当你有多个发出声音的设备的时候】
- [geek](https://geekuninstaller.com/) 【傻瓜式卸载软件】
- [WizTree](https://www.diskanalyzer.com/download) 【速度超快】
- [Autoruns](https://learn.microsoft.com/en-us/sysinternals/downloads/autoruns) 【注册表清理工具，微软提供】
- [ContextMenuManager](https://gitee.com/BluePointLilac/ContextMenuManager/releases)【上下文菜单管理】
- [Motrix](https://motrix.app/zh-CN/)【下载工具】

## 编程环境

### 换源

```pwsh
npm config set registry https://registry.npm.taobao.org
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```

- `.cargo/config.toml`

```toml
[registries]
ustc = { index = "https://mirrors.ustc.edu.cn/crates.io-index/" }

[source.crates-io]
replace-with = 'ustc'

[source.ustc]
registry = "git://mirrors.ustc.edu.cn/crates.io-index"
```
