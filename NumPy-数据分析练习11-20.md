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
