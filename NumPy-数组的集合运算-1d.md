## NumPy 数组的集合运算 1d

数组的集合运算：

- unique(x): 计算x中的唯一元素，并返回有序结果
- intersect1d(x, y): 计算x和y中的公共元素，并返回有序结果
- union1d(x, y): 计算x和y的并集，并返回有序结果
- in1d(x, y): 得到一个表示“x的元素是否包含于y”的布尔型数组
- setdiff1d(x, y): 集合的差，即元素在x中且不在y中
- setxor1d(x, y): 集合的对称差，即存在于一个数组中但不同时存在于两个数组中的元素

**所有的函数是针对一维数组设计的，所以名字后都带有1d**

#### unique(x) 函数：计算x中的唯一元素，并返回有序结果

用于找出数组中的唯一值并返回已排序的结果

```python
import numpy as np

names = np.array(['Bob', 'Joe', 'Will', 'Bob', 'Will', 'Joe', 'Joe'])
print(np.unique(names))
# >>>['Bob' 'Joe' 'Will']

a = np.array([3, 3, 3, 2, 2, 1, 1, 4, 4])
print(np.unique(a))
# >>>[1 2 3 4]

# 纯用python代码：（不用numpy函数）处理唯一化：
print(sorted(set(names)))
# >>>['Bob' 'Joe' 'Will']
print(sorted(set(a)))
# >>>[1 2 3 4]
```

#### intersect1d(x, y) 函数：计算x和y中的公共元素，并返回有序结果

用于计算两个数组x和y的交集，唯一化并排序

```python
import numpy as np
a = np.array([1,1,3,4,5,8,7,9])
b = np.array([1,9,3,2,6,2,5])
print(np.intersect1d(a,b))
# >>>[1 3 5 9]
```

#### union1d(x, y) 函数: 计算x和y的并集，并返回有序结果

用于计算两个数组x和y的并集，唯一化并排序

```python
import numpy as np
a = np.array([1,1,3,4,5,8,7,9])
b = np.array([1,9,3,2,6,2,5])
print(np.intersect1d(a,b))
print(np.union1d(a,b))
# >>>[1 3 5 9]
# >>>[1 2 3 4 5 6 7 8 9]
```

#### in1d(x, y) 函数: 得到一个表示“x的元素是否包含于y”的布尔型数组

用于计算前面的数组是否包含于后面的数组，返回布尔值

```python
import numpy as np
a = np.array([1,1,3,4,5,8,7,9])
b = np.array([1,9,3,2,6,2,5])
print(np.in1d(a,b))
# >>>[ True  True  True False  True False False  True]
# 返回的值是针对第一个参数的数组（x）的，所以维数和第一个参数一致，布尔值与数组的元素位置也一一对应
```

#### setdiff1d(x, y) 函数: 集合的差，即元素在x中且不在y中

用于计算元素存在于第一个数组（x）但不存在于第二个数组（y）中

```python
import numpy as np
a = np.array([1,1,3,4,5,8,7,9])
b = np.array([1,9,3,2,6,2,5])
print(np.setdiff1d(a,b))
# >>>[4 7 8]
```

#### setxor1d(x, y) 函数: 集合的对称差，即存在于一个数组中但不同时存在于两个数组中的元素

集合的对称差：两个集合的交集的补集。

```python
import numpy as np
a = np.array([1,1,3,4,5,8,7,9])
b = np.array([1,9,3,2,6,2,5])
print(np.union1d(a,b))
print(np.intersect1d(a,b))
print(np.setxor1d(a,b))
#[1 2 3 4 5 6 7 8 9]
#[1 3 5 9]
#[2 4 6 7 8]
```
