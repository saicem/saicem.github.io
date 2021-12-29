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

```Python
result = "a > b" if a > b else "a <= b"
```

## python package

### pymysql

> 连接mysql
> 依赖 pip install cryptography

### RandomWords

> [如何使用](https://randomwords.readthedocs.io/en/latest/how_to_use.html)

### [Faker](https://faker.readthedocs.io/en/master/)

- [Locale zh_CN](https://faker.readthedocs.io/en/master/locales/zh_CN.html#faker-providers-address)

```python
from faker import Faker
fake = Faker('zh_CN')
Faker.seed(0)
print(fake.name())
```

### [cacheout](https://cacheout.readthedocs.io/en/latest/)