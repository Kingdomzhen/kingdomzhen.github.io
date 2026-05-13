+++
title = "10 个实用的 Python 技巧"
date = "2026-04-05"
description = "这些 Python 技巧让你的代码更简洁、更高效"
tags = ["Python", "编程", "技巧"]
categories = ["技术"]
+++

## 1. 列表推导式

传统写法：

```python
squares = []
for x in range(10):
    squares.append(x**2)
```

推导式一行搞定：

```python
squares = [x**2 for x in range(10)]
```

## 2. 同时遍历索引和元素

```python
items = ["a", "b", "c"]
for i, item in enumerate(items):
    print(f"{i}: {item}")
```

## 3. 字典合并

```python
a = {"x": 1, "y": 2}
b = {"y": 3, "z": 4}
merged = a | b  # Python 3.9+
# {'x': 1, 'y': 3, 'z': 4}
```

## 4. f-string 格式化

```python
name = "世界"
price = 49.9
print(f"你好，{name}！价格是 ¥{price:.2f}")
```

## 5. 解包赋值

```python
# 交换变量
a, b = b, a

# 多值解包
first, *middle, last = [1, 2, 3, 4, 5]
# first=1, middle=[2,3,4], last=5
```

## 6. 使用 `pathlib` 处理路径

```python
from pathlib import Path

# 比 os.path 更直观
data_dir = Path.home() / "data"
data_dir.mkdir(exist_ok=True)
```

## 7. `defaultdict` 简化计数

```python
from collections import defaultdict

counts = defaultdict(int)
for word in ["a", "b", "a"]:
    counts[word] += 1
```

## 8. `itertools` 组合迭代

```python
from itertools import combinations

for a, b in combinations([1, 2, 3], 2):
    print(a, b)
# (1,2) (1,3) (2,3)
```

## 9. 装饰器计时

```python
import time

def timer(func):
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        print(f"{func.__name__} 耗时 {time.time() - start:.3f}s")
        return result
    return wrapper
```

## 10. `dataclass` 省样板代码

```python
from dataclasses import dataclass

@dataclass
class User:
    name: str
    age: int

u = User("张三", 25)
print(u)  # User(name='张三', age=25)
```

---

这 10 个技巧覆盖了日常开发中的高频场景，熟练使用它们能让你写出更精炼的 Python 代码。
