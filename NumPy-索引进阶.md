# NumPy 索引进阶

## 花式索引

`花式索引`是获取数组中特定元素的有效方法

```python
# 使用特定的索引序列对数组进行索引，返回索引的元素的列表

import numpy as np
# Fancy indexing
a = np.arange(0, 100, 10) # 生成数组[0, 100) 间隔为10
indices = [1, 5, -1]  # 用列表作为参数，进行高效索引。特定索引序列：第[1]个，第[5]个，倒数第一个
b = a[indices]
print(a) # >>>[ 0 10 20 30 40 50 60 70 80 90]
print(b) # >>>[10 50 90]
```

## 缺省索引

`不完全索引`是从多维数组的第一个维度获取索引或切片的一种方便方法

```python
import numpy as np
# Incomplete Indexing
a = np.arange(0, 100, 10)
b = a[:5]
c = a[a >= 50]
print(b) # >>>[ 0 10 20 30 40]
print(c) # >>>[50 60 70 80 90]
```

## Where 函数

`numpy.where()`有两种用法：

- np.where(condition, x, y)：满足条件(condition)，输出x，不满足输出y
- np.where(condition)：只有条件 (condition)，没有x和y，则输出满足条件 (即非0) 元素的坐标 

```python
# Where 方法一：满足条件（参数1），条件为True，输出1；否则为-1

import numpy as np
aa = np.arange(10)
print(np.where(aa,1,-1))  # >>>array([-1,  1,  1,  1,  1,  1,  1,  1,  1,  1])  # 0为False，所以第一个输出-1
print(np.where(aa > 5,1,-1)) # >>>array([-1, -1, -1, -1, -1, -1,  1,  1,  1,  1])
```

```python
# Where 方法二：输出满足条件 (即非0) 元素的坐标

import numpy as np
aa = np.array([2,4,6,8,10])
print(np.where(aa > 5)	)			# 返回索引！！
#>>>(array([2, 3, 4]),)   
print(aa[np.where(aa > 5)]  )			# 等价于 aa[aa>5]，返回的是数组
#>>>array([ 6,  8, 10])

a = np.arange(0, 100, 10) # 生成数组[0, 100) 间隔为10
b = np.where(a < 50) # 返回满足条件的元素坐标
c = np.where(a >= 50) 
d = np.where(a >= 50)[0] # 等价于 读取array中元素

print(a) # >>>[ 0 10 20 30 40 50 60 70 80 90]
print(b) # >>>(array([0, 1, 2, 3, 4]),)
print(c) # >>>(array([5, 6, 7, 8, 9]),)
print(d) # >>>[5 6 7 8 9]
```
