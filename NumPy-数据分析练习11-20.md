## NumPy 数据分析练习

#### 11.获取两个numpy数组之间的公共项

**intersect1d(x, y)函数**: 计算x和y中的公共元素，并返回有序结果

```python
# 获取数组a和数组b之间的公共项

import numpy as np
a = np.array([1,2,3,2,3,4,3,4,5,6])
b = np.array([7,2,10,2,7,4,9,4,9,8])
print(np.intersect1d(a,b))
# >>> [2 4]
```

#### 12.从一个数组中删除存在于另一个数组中的项

**setdiff1d(x, y)**: 集合的差，即元素在x中且不在y中

```python
# 从数组a中删除数组b中的所有项

import numpy as np
a = np.array([1,2,3,4,5])
b = np.array([5,6,7,8,9])
print(np.setdiff1d(a,b))# From 'a' remove all of 'b'
# >>> [1 2 3 4]
```

#### 补充知识: [NumPy 数组的集合运算 1d](https://github.com/tywcx/Learn-by-doing/blob/main/NumPy-%E6%95%B0%E7%BB%84%E7%9A%84%E9%9B%86%E5%90%88%E8%BF%90%E7%AE%97-1d.md)

#### 13.得到两个数组元素匹配的位置

使用**where**函数，返回的是索引位置

```python
# 获取a和b元素匹配的位置

**import numpy as np
a = np.array([1,2,3,4,5])
b = np.array([5,6,7,8,9])
print(np.setdiff1d(a,b))# From 'a' remove all of 'b'**
# >>> (array([1, 3, 5, 7]),)
```

#### 补充知识: [Numpy 索引进阶](https://github.com/tywcx/Learn-by-doing/blob/main/NumPy-%E7%B4%A2%E5%BC%95%E8%BF%9B%E9%98%B6.md)

#### 14.从numpy数组中提取给定范围内的所有数字

使用**where**函数，返回的是索引位置; 使用`a[np.where(condition)]`返回的是数组元素

```python
# 获取a和b元素匹配的位置
import numpy as np
a = np.array([2, 6, 1, 9, 10, 3, 27])
print(a[np.where((a>=5) & (a<=10))])
# >>> [ 6  9 10]

# Method 2:
index = np.where(np.logical_and(a>=5, a<=10))
print(a[index])
# >>> [ 6  9 10]

# Method 3: 
print(a[(a >= 5) & (a <= 10)])
# >>> [ 6  9 10]

```

#### 补充知识: [np.where和np.logical_and/or/not](https://github.com/tywcx/Learn-by-doing/blob/main/NumPy-where%E5%92%8Clogical%E5%87%BD%E6%95%B0.md)

