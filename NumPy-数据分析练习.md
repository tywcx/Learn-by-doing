## NumPy 数据分析练习

参考[数据分析练习](https://numpy.org.cn/article/advanced/numpy_exercises_for_data_analysis.html#numpy%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E9%97%AE%E7%AD%94)

#### 1.导入numpy作为np，并查看版本

```python
# 将numpy导入为 np 并打印版本号

import numpy as np 
print(np.__version__)

#output
#1.19.2
```

#### 2.创建一维数组

```python

# 创建从0到4的一维数字数组

import numpy as np 
arr = np.arange(5) # 注意：np.
print(arr)

#output
#[0 1 2 3 4]
```

#### 3.创建一个布尔数组

```python
#创建一个numpy数组元素值全为True（真）的数组

#方法一：使用full函数
import numpy as np 
arr = np.full((2,2),True)
#np.full((2, 2), True, dtype=bool)
print(arr)

#方法二：使用ones函数
arr=np.ones((2,2), dtype=bool)
print(arr)

#output
#[[ True  True]
# [ True  True]]
```

#### 补充知识: [创建 Numpy 数组的不同方式](https://github.com/tywcx/Learn-by-doing/edit/main/NumPy-%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E7%BB%83%E4%B9%A0-%E8%A1%A5%E5%85%85%E7%9F%A5%E8%AF%861.md)

#### 4.从一维数组中提取满足指定条件的元素

```python
# 从 arr 中提取所有的奇数

import numpy as np
# Input
arr=np.arange(10)
print(arr)

# Solution
arr[arr%2==1]   # 注意：无赋值操作 arr不变
print(arr)

arr=arr[arr%2==1] # 0-9 数字与下标刚好一一对应
print(arr)


#output
#[0 1 2 3 4 5 6 7 8 9]
#[0 1 2 3 4 5 6 7 8 9]
#[1 3 5 7 9]
```

#### 5. 用numpy数组中的另一个值替换满足条件的元素项

```python
#将arr中的所有奇数替换为-1

import numpy as np
# Input
arr=np.arange(10)
print(arr)
# Solution
arr[arr%2==1]=-1
print(arr)


#output
#[0 1 2 3 4 5 6 7 8 9]
#[ 0 -1  2 -1  4 -1  6 -1  8 -1]
```

#### 6. 在不影响原始数组的情况下替换满足条件的元素项

```python
#将arr中的所有奇数替换为-1，而不改变arr

import numpy as np
# Input
arr=np.arange(10)
print(arr)
# Solution
res=np.where(arr % 2 == 1, -1, arr)
print('arr:',arr,'\n','res:',res)

#output
#[0 1 2 3 4 5 6 7 8 9]
#arr: [0 1 2 3 4 5 6 7 8 9] 
#res: [ 0 -1  2 -1  4 -1  6 -1  8 -1]
```
#### 补充知识: [索引进阶](https://github.com/tywcx/Learn-by-doing/blob/main/NumPy-%E7%B4%A2%E5%BC%95%E8%BF%9B%E9%98%B6.md)

#### 7. 改变数组的形状

```python
# 将一维数组转换为2行的2维数组

import numpy as np
a = np.arange(10)
print(a)
# print(a.reshape(2,5))
print(a.reshape(2,-1)) # Setting to -1 automatically decides the number of cols

#output
#[0 1 2 3 4 5 6 7 8 9]
#[[0 1 2 3 4]
# [5 6 7 8 9]]
```

#### 8. 垂直叠加两个数组

```python
# 垂直堆叠数组a和数组b (行拼接)

import numpy as np
 
a = np.arange(10).reshape(2,-1)
b = np.repeat(1, 10).reshape(2,-1)
print(a)
print(b)
print('M1:',np.concatenate((a, b))) # Method 1
print('M2:',np.r_[a, b])  # Method 2
print('M3:',np.append(a, b, axis=0))  # Method 3
print('M4:',np.vstack((a, b)))  # Method 4

#output
#[[0 1 2 3 4]     # a
# [5 6 7 8 9]]

#[[1 1 1 1 1]   # b
# [1 1 1 1 1]]

#[[0 1 2 3 4]   # M1-M4 
# [5 6 7 8 9]
# [1 1 1 1 1]
# [1 1 1 1 1]]
```

#### 9. 水平叠加两个数组

```python
# 将数组a和数组b水平堆叠 (列拼接)

import numpy as np
 
m = np.arange(10).reshape(2,-1)
n = np.repeat(1, 10).reshape(2,-1)
print(m)
print(n)
print('M1:',np.append(m, n, axis=1))
print('M2:',np.c_[m, n])
print('M3:',np.concatenate((m, n), axis=1))
print('M4:',np.hstack((m, n)))

#output
#[[0 1 2 3 4]     # a
# [5 6 7 8 9]]

#[[1 1 1 1 1]   # b
# [1 1 1 1 1]]
  
#[[0 1 2 3 4 1 1 1 1 1] # M1-M4 
#  [5 6 7 8 9 1 1 1 1 1]]
```

#### 补充知识: [拼接Numpy数组的不同方式](https://github.com/tywcx/Learn-by-doing/blob/main/NumPy-%E6%8B%BC%E6%8E%A5Numpy%E6%95%B0%E7%BB%84%E7%9A%84%E4%B8%8D%E5%90%8C%E6%96%B9%E5%BC%8F.md)


#### 10.在无硬编码的情况下生成numpy中的自定义序列

```python
# 创建以下模式而不使用硬编码。只使用numpy函数和下面的输入数组a

import numpy as np

a=np.array([1,2,3])

print('M1:',np.r_[np.repeat(a,3), np.tile(a,3)])  # Method 1
print('M2:',np.append(np.repeat(a,3), np.tile(a,3), axis=0))  # Method 2

#output
#[1 1 1 2 2 2 3 3 3 1 2 3 1 2 3 1 2 3]
```

#### 补充知识: [对Numpy数组元素的复制操作](https://github.com/tywcx/Learn-by-doing/blob/main/NumPy-%E5%AF%B9Numpy%E6%95%B0%E7%BB%84%E5%85%83%E7%B4%A0%E7%9A%84%E5%A4%8D%E5%88%B6%E6%93%8D%E4%BD%9C.md)

