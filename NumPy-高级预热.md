# NumPy 基础补充，高级预热


## Tile

功能是：重复数组

tile(A, reps):

A---源数组

### reps---方向次数，例如reps=2：就是重复2次源数组

#### Case 1：一维数组

```python
a = np.array([1,2,3])
print ("a:\n", a)
b = np.tile(a,2) #b = np.tile(a,(1,2))同结果
print ("b:\n", b)
```

一维数组:复制后返回的也是一维数组

```
a:
 [1 2 3]
b:
 [1 2 3 1 2 3]
```

#### Case 2：二维数组

```python
a = np.array([[1,2], [3,4]])
print ("a:\n", a)
b = np.tile(a,2) 
print ("b:\n", b)
```

二维数组:复制后返回的也是二维数组

```
a:
 [[1 2]
 [3 4]]
b:
 [[1 2 1 2]
 [3 4 3 4]]
```


### reps---方向次数，例如reps=(2,3)：变成二维数组，二维数组内的一维数组复制2次，一维数组的元素复制3次

#### Case 1：一维数组

```python
a = np.array([1,2,3])
print ("a:\n", a)
b = np.tile(a,2) #一维数组:复制后返回的也是一维数组
print ("b:\n", b)

a = np.array([1,2,3])
print ("a:\n", a)
b = np.tile(a,(2,3)) #一维数组:复制后返回的是二维数组（2行9列）：即源数组行复制2次（沿纵轴方向），在列复制3次（沿横轴方向）
print ("b:\n", b)
```


```
a:
 [1 2 3]
b:
 [1 2 3 1 2 3]
 
 vs
 
 a:
 [1 2 3]
b:
 [[1 2 3 1 2 3 1 2 3]
 [1 2 3 1 2 3 1 2 3]]
```

#### Case 2：二维数组

```python
a = np.array([[1,2], [3,4]])
print ("a:\n", a)
b = np.tile(a,2) #二维数组:复制后返回的也是二维数组
print ("b:\n", b)

a = np.array([[1,2], [3,4]])
print ("a:\n", a)
b = np.tile(a,(2,3)) #二维数组:复制后返回的是二维数组（4行6列）：即源数组行复制2次（沿纵轴方向），在列复制3次（沿横轴方向）
print ("b:\n", b)
```


```
a:
 [[1 2]
 [3 4]]
b:
 [[1 2 1 2]
 [3 4 3 4]]
 
vs

a:
 [[1 2]
 [3 4]]
b:
 [[1 2 1 2 1 2]
 [3 4 3 4 3 4]
 [1 2 1 2 1 2]
 [3 4 3 4 3 4]]
```

**reps=(n,m) -- 结论：先自我复制m次--->整个复制n次**

```python
x = np.array([[1,2], [3,4]])
y = np.array([5, 6])
addent = np.tile(y, (len(x), 1))
print ("addent: \n", addent, )
z = x + addent
print ("z:\n", z)
```

```
addent: 
 [[5 6]
 [5 6]]
z:
 [[ 6  8]
 [ 8 10]]
```

## Broadcast

广播(Broadcast)是 numpy 对不同形状(shape)的数组进行数值计算的方式， 对数组的算术运算通常在相应的元素上进行。

但是很多情况下不需要使用,在进行矩阵加减运算的时候会自动复制

```python
x = np.array([[1,2], [3,4]])
y = np.array([5, 6])
z = x + y
print ("z:\n", z)
z = x - y
print ("z:\n", z)
```

```
z:
 [[ 6  8]
 [ 8 10]]
z:
 [[-4 -4]
 [-2 -2]]
```

## Reshap

给数组一个新的形状而不改变其数据：numpy.reshape(a, newshape)

```python
x = np.array([[1,2], [3,4], [5,6]])
print ("x: \n", x)
print ("x.shape: ", x.shape) #shape描述的是矩阵的形状
y = np.reshape(x, (2, 3))
print ("y.shape: ", y.shape)
print ("y: \n", y)
```

```
x: 
 [[1 2]
 [3 4]
 [5 6]]
x.shape:  (3, 2) #二维：3行2列
y.shape:  (2, 3)
y: 
 [[1 2 3]
 [4 5 6]]
```

## squeeze

numpy.squeeze(a, axis=None)

squeeze()函数的功能是：从矩阵shape中，去掉维度为1的。例如一个矩阵是的shape是（5， 1），使用过这个函数后，结果为（5，）

```python
x = np.array([[[1,2,1]],[[2,2,3]]])
print ("x: \n", x)
print ("x.shape: ", x.shape)
y = np.squeeze(x, 1) # squeeze dim 1
print ("y.shape: ", y.shape) 
print ("y: \n", y)
```

```
x: 
 [[[1 2 1]]

 [[2 2 3]]]
x.shape:  (2, 1, 3) # 三维：2行，每行3列
y.shape:  (2, 3)  #二维：2行3列
y: 
 [[1 2 1]
 [2 2 3]]
```

## expand_dims

expand_dims(a, axis)中，a为numpy数组，axis为需添加维度的轴，a.shape将在该轴显示为1

#### Case 1：一维数组：即向量

```python
x = np.array([1,2,3])
print ("x: \n", x)
print ("x.shape: ", x.shape)
y = np.expand_dims(x, axis=0) # expand dim 1 
print ("y.shape: ", y.shape) 
print ("y: \n", y)
y = np.expand_dims(x, axis=1) # expand dim 1
print ("y.shape: ", y.shape) 
print ("y: \n", y)
```


```
x: 
 [1 2 3]
x.shape:  (3,) # 一维：对应的shape为3，axis=1对应的shape为空
y.shape:  (1, 3) # 设置axis为0，即在axis=0添加维度,即矩阵从一维矩阵变成了1*3的二维矩阵
y: 
 [[1 2 3]]
y.shape:  (3, 1) #在axis=1添加维度，即矩阵从一维矩阵变成了3*1的二维矩阵
y: 
 [[1]
 [2]
 [3]]
```





#### Case 2：二维数组

```python
x = np.array([[1,2,1],[2,2,3]])
print ("x: \n", x)
print ("x.shape: ", x.shape)
y = np.expand_dims(x, axis=0) # expand dim 1
print ("y.shape: ", y.shape) 
print ("y: \n", y)
y = np.expand_dims(x, 1) # expand dim 1 （axis=1）
print ("y.shape: ", y.shape) 
print ("y: \n", y)
```



```
x: 
 [[1 2 1]
 [2 2 3]]
x.shape:  (2, 3) # shape中2处于axis=0的位置，3处于axis=1的位置
y.shape:  (1, 2, 3) # 设置axis为0，矩阵从2*3的二维矩阵变成了1*2*3的三维矩阵
y: 
 [[[1 2 1]
  [2 2 3]]]
y.shape:  (2, 1, 3) # 设置axis为1，矩阵从2*3的二维矩阵变成了2*1*3的三维矩阵
y: 
 [[[1 2 1]]

 [[2 2 3]]]
```
