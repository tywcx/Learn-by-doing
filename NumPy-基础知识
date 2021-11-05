# NumPy

### NumPy Array, dtype, size, and shape

```
import numpy as np
```

```python
# 1-D Array
a = np.array([1, 2, 3])
print(a)
print(a.shape)
print(a.size)
print(a.dtype)

b = np.array([1.3 , 2.2 , 1.7])
print ("b: ", b)
print ("b shape:", b.shape)
print ("b size: ", b.size)
print ("b dtype: ", b.dtype) # notice the float datatype
```


```
[1 2 3]
(3,)  # 形状：一维：包含3个元素的数组
3
int64

b:  [1.3 2.2 1.7]
b shape: (3,)     # 形状：一维：包含3个元素的数组
b size:  3
b dtype:  float64
```


```python
c = np.array([[1, 2, 3], [4, 5, 6]])
print('c:', c)
print(c.shape)
print(c.size)
print(c.dtype)

# 3-D array (matrix)
x = np.array([[[1,2,3], [4,5,6], [7,8,9]]])
print ("x:", x)
print ("x shape:", x.shape)
print ("x size: ", x.size)
print ("x dtype: ", x.dtype)


x1 = np.array([[[1,2,3], [4,5,6]], 
                [[7,8,9],[10,11,12]]])
print ("x1:\n", x)
print ("x1 shape:", x1.shape)
print ("x1 size: ", x1.size)
print ("x1 dtype: ", x1.dtype)
```


```
c: [[1 2 3]
 [4 5 6]]
(2, 3)  #形状：2维数组：2行3列
6
int64

x:
 [[[1 2 3]
  [4 5 6]
  [7 8 9]]]
x shape: (1, 3, 3)  #形状：3维数组：一个1行，包含（3*3矩阵）三行三列 
x size:  9
x dtype:  int64

x1:
 [[[1 2 3]
  [4 5 6]
  [7 8 9]]]
x1 shape: (2, 2, 3) #形状：3维数组：一个2行，每行包含一个2行3列（2*3矩阵） 
x1 size:  12
x1 dtype:  int64
```

### NumPy Functions

```python
print ("np.zeros((2,2)):\n", np.zeros((2,2)))#创建一个2行2列的数组 全为0
print ("np.ones((2,2)):\n", np.ones((2,2)))#创建一个2行2列的数组 全为1
print ("np.eye((2)):\n", np.eye((2)))#返回一个对角线上全是1，而其他位置全为0的一个二维数组
print ("np.random.random((2,2)):\n", np.random.random((2,2))) #创建一个随机值数组 它为每个元素分配0到1之间的随机值
```

```
np.zeros((2,2)):
 [[0. 0.]
 [0. 0.]]
np.ones((2,2)):
 [[1. 1.]
 [1. 1.]]
np.eye((2)):
 [[1. 0.]
 [0. 1.]]
np.random.random((2,2)):  
 [[0.35025319 0.39167864]
 [0.59879892 0.34717697]]
 ```


### NumPy Indexing


#### Indexing 索引

```python
my_array = np.array([1, 2, 3, 4, 5]) 
print(my_array)
print(my_array[0])
print(my_array[1])
my_array[0] = -1
print(my_array)
```

```
[1 2 3 4 5]
1
2
[-1  2  3  4  5]
```


 
 
