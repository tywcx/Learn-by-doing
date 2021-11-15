## NumPy 数据分析练习

#### 11.获取两个numpy数组之间的公共项

```python
# 获取数组a和数组b之间的公共项

import numpy as np
a = np.array([1,2,3,2,3,4,3,4,5,6])
b = np.array([7,2,10,2,7,4,9,4,9,8])
print(np.intersect1d(a,b))
# > > > [2 4]
```

#### 补充知识: [NumPy 数组的集合运算 1d](https://github.com/tywcx/Learn-by-doing/blob/main/NumPy-%E6%95%B0%E7%BB%84%E7%9A%84%E9%9B%86%E5%90%88%E8%BF%90%E7%AE%97-1d.md)
