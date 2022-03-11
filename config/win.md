# win

此文档用于重置`Windows`后快速配置环境。

## 设置

### 基本设置

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

## 工具

- [PowerToys](https://docs.microsoft.com/zh-cn/windows/powertoys/)

### office

- [office tool plus](https://otp.landian.vip/zh-cn/)

### 录屏

- [screen to gif](https://github.com/NickeManarin/ScreenToGif)
- [Captura](https://github.com/MathewSachin/Captura)
  > Captura 好东西！可惜维护者已经放弃了，万恶的 copy cat ！！！


#### 桌面格子

- [Fences](https://www.stardock.com/products/fences/)
  > 付费的🙄，我只想要格子，不想要什么贴边自动收缩什么的功能...
- [腾讯桌面整理](https://guanjia.qq.com/product/zmzl/)
  > 注意是`下载桌面整理独立版`
- [Coodesker](https://www.coodesker.com/)
  > 酷呆桌面 简洁 虽然在[Github](https://github.com/coodesker/coodesker-desktop)上，但并不开源

#### 压缩

- [Bandzip](http://www.bandisoft.com/)
- [7z](https://www.7-zip.org/)

### 开发

- [VS CODE](https://code.visualstudio.com/)
- [Visual Studio](https://visualstudio.microsoft.com/zh-hans/)
- [Git](https://git-scm.com/download/win)
- [mingw-w64](http://mingw-w64.org/doku.php/download)
  > 它会让你在这[下载](https://sourceforge.net/projects/mingw-w64/files/mingw-w64/mingw-w64-release/)  
- [Python](https://www.python.org/downloads/)
  > 设置清华源`pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple`
- [go](https://golang.org/)
  
  ```pwsh
  # 设置模块代理
  go env -w GO111MODULE=on
  go env -w GOPROXY=https://goproxy.cn,direct
  ```

- [winget](https://docs.microsoft.com/en-us/windows/package-manager/winget/)
  > win11 起系统内置

- [oh my posh](https://ohmyposh.dev/)

  ```ps1
  Import-Module posh-git
  Import-Module oh-my-posh
  Set-PoshPrompt -Theme  wopian
  ```

- [Sublime Merge](https://www.sublimemerge.com/)
- Typora
- WEB测试
  - Postman
  - ApiFox
- [WinSCP](https://winscp.net/eng/docs/lang:chs)
- [DBeaver](https://dbeaver.io/)
- [BloomRpc](https://github.com/bloomrpc/bloomrpc)

### 日常使用

- [TIM](https://office.qq.com/download.html)
- [V2rayN](https://github.com/2dust/v2rayN/releases)
- [fluent-reader](https://github.com/yang991178/fluent-reader)
  > rss 阅读

### 浏览器插件

#### Edge

- Adblock plus
- Tampermonkey
- 哔哩哔哩助手
- 草料二维码
- Vimium C

### 清理

- CCleaner
- [geek](https://geekuninstaller.com/)
- [WizTree](https://www.diskanalyzer.com/download)
  > 中文界面，速度快
- Autoruns(注册表清理工具)

### 其它

- OCTAVE
  > 开源软件 代替 MATLAB
- 达芬奇 DaVinci
- VirtualBox
- [PotPlayer](https://potplayer.daum.net/?lang=zh_CN)
- Axure
- [draw.io](https://app.diagrams.net/)
