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

#### 补充知识：创建 Numpy 数组的不同方式

创建Numpy数组有三种不同的方法：

- 使用Numpy内部功能函数
- 从列表等其他Python的结构进行转换
- 使用特殊的库函数

##### 使用Numpy内部功能函数

###### 创建一维数组

使用arange函数，快速创建数组

```python
import numpy as np 
array = np.arange(6)  # 将值6传递给arange函数会创建一个值范围为0到5的数组
print(array, '\n', array.shape,'\n', array[2]) #用shape 验证此数组的维度
array[2]=6    # Numpy的数组是可变的
print(array, '\n', array.shape)


#output
#[0 1 2 3 4 5] 
#(6,)     # 由于逗号后面没有值，因此这是一维数组
#2
#[0 1 6 3 4 5] 
#(6,)
```

**与Python列表不同，Numpy数组的内容是同质的。 将字符串值分配给数组中的元素，其数据类型为int，则会出现错误。**

```
array[2] ='Numpy' ## 报错！！ValueError

#python list:
list = [0, 1,'Numpy', 3,4,5]
print(list)

#output
#[0, 1, 'Numpy', 3, 4, 5]
```

###### 创建二维数组

使用arange函数，输出一维数组

要使其成为二维数组，再使用reshape函数链接其输出

```python
import numpy as np
array = np.arange(6).reshape(2,3) # 先创建6个整数，然后将数组转换为具有2行和3列的二维数组
print(array, '\n', array.shape, '\n', array[1][2])#用shape 验证此数组的维度

#output
#[[0 1 2]
#[3 4 5]] 
#(2, 3) # 得到两个值，这是一个二维数组
#5
```

###### 创建三维数组

要创建三维数组，reshape 函数指定3个参数

```python
import numpy as np
array = np.arange(27).reshape(3,3,3)  # 需要注意的是：数组中元素的数量（27）必须是其尺寸（3*3*3）的乘积
print(array, '\n', array.shape, '\n', array[1][2][2])  # 要交叉检查它是否是三维数组 使用shape
```

```
#output
[[[ 0  1  2]
  [ 3  4  5]
  [ 6  7  8]]

 [[ 9 10 11]
  [12 13 14]
  [15 16 17]]

 [[18 19 20]
  [21 22 23]
  [24 25 26]]] 
 (3, 3, 3) 
 17
```

###### 使用arange函数 创建一个在定义的起始值和结束值之间具有特定序列的数组

```python
import numpy as np
array=np.arange(1, 10, 3)
print(array)

#output
#[1 4 7]
```

###### 使用其他Numpy函数

- 使用```zeros```函数创建一个填充零的数组，函数的参数表示行数和列数（或其维数）
- 使用```ones```函数创建一个填充了1的数组
- 使用```empty```函数创建一个数组。它的初始内容是随机的，取决于内存的状态
- 使用```full```函数创建一个填充给定值的n * n数组
- 使用```eye```函数可以创建一个n * n矩阵，对角线为1，其他为0
- 使用```linspace```函数在指定的时间间隔内返回均匀间隔的数字


```python
import numpy as np
array=np.zeros((2,4))
print(array)
array=np.ones((2,4))
print(array)
array=np.empty((2,4))
print(array)
array=np.full((2,2), 3)
print(array)
array=np.eye(3,3)
print(array)
array=np.linspace(0, 10, num=4)
print(array)
array=np.linspace(0, 10, num=5)
print(array)
```

```
#output
[[0. 0. 0. 0.]
 [0. 0. 0. 0.]]
[[1. 1. 1. 1.]
 [1. 1. 1. 1.]]
[[1. 1. 1. 1.]
 [1. 1. 1. 1.]]
[[3 3]
 [3 3]]
[[1. 0. 0.]
 [0. 1. 0.]
 [0. 0. 1.]]
[ 0.          3.33333333  6.66666667 10.        ]
[ 0.   2.5  5.   7.5 10. ]
```


