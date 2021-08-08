# python笔记

## pip

```shell
pip freeze > requirements.txt
# 导出当前环境配置
pip install -r requirements.txt -t .
# 根据 requirements.txt 安装包到当前文件夹
pip uninstall -r python_modules.txt -y
# 删除包
```

### 使用清华源

```shell
pip install 要安装的包 -i https://pypi.tuna.tsinghua.edu.cn/simple
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```

## 选择表达式

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

## python package

### pymysql

> 连接mysql
> 依赖 pip install cryptography

### RandomWords

> <https://randomwords.readthedocs.io/en/latest/how_to_use.html>

### black

> 格式化

### fastapi

> 快速api开发

### uvicorn

> 配合 fastapi 尚未研究

### [Faker](https://faker.readthedocs.io/en/master/)

- [Locale zh_CN](https://faker.readthedocs.io/en/master/locales/zh_CN.html#faker-providers-address)

```shell
from faker import Faker
fake = Faker('zh_CN')
Faker.seed(0)
print(fake.name())
```
