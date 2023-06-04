# 在 Ubuntu 上安装 Python

```bash
cd /tmp
app="3.10"
apd="3.10.11"
sudo apt update && sudo apt upgrade -y
sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev
# 查看 https://www.python.org/downloads/ 下载最新版本
wget "https://www.python.org/ftp/python/${apd}/Python-${apd}.tar.xz"
tar -xf Python-${apd}.tar.xz

# 编译安装
cd "Python-${apd}"
sudo ./configure --enable-optimizations --prefix="/usr/local/apk/python${app}"
sudo make
sudo make altinstall 2>&1 | tee make_install.log
python${app} -V
```

## 配置命令

```bash
sudo update-alternatives --install /usr/bin/python3 python3 /usr/local/bin/python${app} 1
sudo update-alternatives --config python3
python3 -V
```

## 卸载

安装目录下 `make uninstall`，或者重新编译 `xargs rm < install_manifest.txt`
