## NumPy 数据分析练习

参考[数据分析练习](https://numpy.org.cn/article/advanced/numpy_exercises_for_data_analysis.html#numpy%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E9%97%AE%E7%AD%94)

#### 1.导入numpy作为np，并查看版本

```python
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


