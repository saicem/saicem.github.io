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

## Terminal配置

- [美化 PowerShell 7 - 安裝 Oh My Posh + 各種好用的插件](https://blog.kwchang0831.dev/blog/dev-env/pwsh-oh-my-posh)
- [Windows 终端提示与技巧](https://docs.microsoft.com/zh-cn/windows/terminal/tips-and-tricks)

- [自定义终端指南](https://docs.microsoft.com/zh-cn/windows/terminal/custom-terminal-gallery/custom-schemes)

- [PowerShell 配置文件](https://docs.microsoft.com/zh-cn/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-7.1)

- [Custom actions in Windows Terminal](https://docs.microsoft.com/zh-cn/windows/terminal/customize-settings/actions)

### Terminal 常用快捷键

- `alt+shift+plus` 新垂直窗格
- `alt+shift+-` 新水平窗格
- 按住`alt`键即可切换窗格
- 按住`alt+shift`并使用箭头键调整焦点窗格的大小
- 键入`ctrl+shift+w`来关闭焦点窗格
- `ctrl+shift+t` New tab
- `ctrl+tab` Open next tab
- `ctrl+shift+tab` Open previous tab

### [oh my posh](https://ohmyposh.dev/)

```ps1
Import-Module posh-git
Import-Module oh-my-posh
Set-PoshPrompt -Theme  wopian
```

## 软件

- [PowerToys](https://docs.microsoft.com/zh-cn/windows/powertoys/)
- [office tool plus](https://otp.landian.vip/zh-cn/)【装office很方便】
- [Captura](https://github.com/MathewSachin/Captura)
- [Coodesker](https://www.coodesker.com/)【在[Github](https://github.com/coodesker/coodesker-desktop)上，但并不开源】
- [Bandzip](http://www.bandisoft.com/)
- [7z](https://www.7-zip.org/)
- [VS CODE](https://code.visualstudio.com/)
- [Visual Studio](https://visualstudio.microsoft.com/zh-hans/)
- [Git](https://git-scm.com/download/win)
- ApiFox
- [WinSCP](https://winscp.net/eng/docs/lang:chs)
- [DBeaver](https://dbeaver.io/)
- [BloomRpc](https://github.com/bloomrpc/bloomrpc)
- [TIM](https://office.qq.com/download.html)
- [V2rayN](https://github.com/2dust/v2rayN/releases)
- [fluent-reader](https://github.com/yang991178/fluent-reader)【rss 阅读】
- CCleaner
- [geek](https://geekuninstaller.com/)【傻瓜式卸载软件】
- [WizTree](https://www.diskanalyzer.com/download) 【中文界面，速度快】
- Autoruns【注册表清理工具】
- OCTAVE【开源软件 代替 MATLAB】
- 达芬奇 DaVinci
- [PotPlayer](https://potplayer.daum.net/?lang=zh_CN)
- Axure
- [draw.io](https://app.diagrams.net/)

## 编程语言

- [Python](https://www.python.org/downloads/)
  > 设置清华源`pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple`
- [go](https://golang.org/)
- [C](https://nuwen.net/mingw.html)
- [mingw-w64](http://mingw-w64.org/doku.php/download)
  > 它会让你在这[下载](https://sourceforge.net/projects/mingw-w64/files/mingw-w64/mingw-w64-release/)

```pwsh
# 设置模块代理
go env -w GO111MODULE=on
go env -w GOPROXY=https://goproxy.cn,direct
```

## 浏览器插件

- Adblock plus
- Tampermonkey
- 草料二维码 【方便的在电脑处理二维码】
- Vimium C
- iTab【漂亮的浏览器起始页】
- uBlacklist 【拒绝内容农场】