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