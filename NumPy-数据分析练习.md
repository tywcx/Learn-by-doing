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

