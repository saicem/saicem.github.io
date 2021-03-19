---
title: python笔记<br>
date: 2021-02-20 21:16:11
---
# pip
```shell
pip freeze > requirements.txt
# 导出当前环境配置
pip install -r requirements.txt -t .
# 根据 requirements.txt 安装包到当前文件夹
```

## 使用清华源

写入用户文件夹下的pip文件夹下的pip.ini文件
```
[global]
index-url = https://pypi.tuna.tsinghua.edu.cn/simple
```

或
```
pip install 要安装的包 -i https://pypi.tuna.tsinghua.edu.cn/simple
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```

# 选择表达式

**先定义变量：**

```Python
a = 1
b = 2
```

**第一种写法：**

```Python
erroStr = "More" if a > b else "Less"
print(erroStr) # 运行结果为：Less
```

**第二种写法：**

```Python
print({True: "More", False: "Less"}[a > b]) # 运行结果为：Less
```

**第三种写法：**

```Python
print(("FalseValue", "TrueValue")[a > b]) # 运行结果为：FalseValue
```