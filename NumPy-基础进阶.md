# NumPy 基础进阶


## Slicing 切片
  
```python
x = np.array([[1,2,3,4], [5,6,7,8], [9,10,11,12]])
print (x, '\n',x.shape)
print ("x column 1: ", x[:, 1]) #输出第二列
print ("x row 0: ", x[0, :]) #输出第一行
print ("x rows 0,1,2 & cols 1,2: \n", x[:3, 1:3]) #输出第一、二、三行，第二、三列
```

```
[[ 1  2  3  4]
 [ 5  6  7  8]
 [ 9 10 11 12]] 
 (3, 4) #二维数组shape：3行4列
x column 1:  [ 2  6 10]
x row 0:  [1 2 3 4]
x rows 0,1,2 & cols 1,2: 
 [[ 2  3]
 [ 6  7]
 [10 11]]
```


## Numpy array & arange 

#### array:

括号内部直接写数组```[a,b,…]```，数组维度随着```[]```嵌套层数增加而增加

```python
a=np.array([1,2,3])
b=np.array([[1,2,1],[2,3,2]])
c=np.array([[[1,2,3],[4,5,6]],[[7,8,9],[0,1,2]],[[3,4,5],[6,7,8]]])
print (a, '\n','a.shape:',a.shape)
print (b, '\n','b.shape:',b.shape)
print (c, '\n','c.shape:',c.shape)
```

```
[1 2 3] 
 a.shape: (3,)  #一维数组：3个元素
[[1 2 1]
 [2 3 2]] 
 b.shape: (2, 3)  #二维数组：2行3列
[[[1 2 3]
  [4 5 6]]

 [[7 8 9]
  [0 1 2]]

 [[3 4 5]
  [6 7 8]]] 
 c.shape: (3, 2, 3) #三维数组：共3行，每行2行3列
```


#### arange:


```python
a=np.arange(5)  #一个参数（**左闭右开**）
b=np.arange(1,5)  #两个参数（**左闭右开**）
c=np.arange(0,5,0.5)  #三个参数：间隔0.5
print(a,'\n',b,'\n',c)

#output

#[0 1 2 3 4] #一个参数=>生成数组（**左闭右开**）
#[1 2 3 4]   #两个参数=>生成数组（**左闭右开**）
#[0.  0.5 1.  1.5 2.  2.5 3.  3.5 4.  4.5]  #三个参数：间隔0.5
```

## Integer array indexing 整数索引

```python
x = np.array([[1,2,3,4], [5,6,7,8], [9,10,11,12]])
print(x)
rows_to_get = np.arange(len(x)) #左闭右开
print ("rows_to_get: ", rows_to_get)
cols_to_get = np.array([0, 2, 1]) #创建数组
print ("cols_to_get: ", cols_to_get)
print ("indexed values: ", x[rows_to_get, cols_to_get])
```

```
[[ 1  2  3  4]
 [ 5  6  7  8]
 [ 9 10 11 12]]
rows_to_get:  [0 1 2]
cols_to_get:  [0 2 1]
indexed values:  [ 1  7 10] #第0行0列：1；第1行2列：7；第2行1列：10
```

## Boolean array indexing 布尔值索引

```python
x = np.array([[1,2], [3, 4], [5, 6]])
print ("x:\n", x)
print ("x > 2:\n", x > 2)
print ("x[x > 2]:\n", x[x > 2])
```

```
x:
 [[1 2]
 [3 4]
 [5 6]]
x > 2:
 [[False False]
 [ True  True]
 [ True  True]]
x[x > 2]:
 [3 4 5 6]
```
