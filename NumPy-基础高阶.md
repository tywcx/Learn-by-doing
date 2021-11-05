# NumPy 基础高阶


## Basic math

```python
a = np.array([[1.0, 2.0], [3.0, 4.0]]) 
b = np.array([[5.0, 6.0], [7.0, 8.0]]) 
sum = a + b 
sub = a - b 
mul = a * b 
quo = a / b 
print("Sum = \n", sum )
print("Sub = \n", sub )
print("Mul = \n", mul )
print("Quo = \n", quo )

#output
#Sum = [[ 6. 8.] [10. 12.]]
#Sub = [[-4. -4.] [-4. -4.]]
#Mul = [[ 5. 12.] [21. 32.]]
#Quo = [[0.2 0.33333333] [0.42857143 0.5 ]]
```

```python
x = np.array([[1,2], [3,4]], dtype=np.float64)
y = np.array([[1,2], [3,4]], dtype=np.float64)
print ("x + y:\n", np.add(x, y),'\n', x + y) 
print ("x - y:\n", np.subtract(x, y),'\n',  x - y) 
print ("x * y:\n", np.multiply(x, y),'\n',  x * y) 
```

```
x + y:
 [[2. 4.]
 [6. 8.]] 
 [[2. 4.]
 [6. 8.]]
x - y:
 [[0. 0.]
 [0. 0.]] 
 [[0. 0.]
 [0. 0.]]
x * y:
 [[ 1.  4.]
 [ 9. 16.]] 
 [[ 1.  4.]
 [ 9. 16.]]
```

**乘法运算符执行逐元素乘法,而不是矩阵乘法; 要执行矩阵乘法，可以使用点积**

## Dot product 点积

- 一维数组：两数组的內积
  - d 和 e 均为一维向量，且均包含有n个元素，则d与e的点积为：
  
  ```A[0]*B[0]+A[1]*B[1]+...+A[n]*B[n]```

```python
d=np.arange(0,9)
e=d[::-1]
print('d:\n',d)
print('e:\n',e)
print(np.dot(d,e))
```

```
d:
 [0 1 2 3 4 5 6 7 8]
e:
 [8 7 6 5 4 3 2 1 0]
84 #84=0*8+1*7+2*6+...+7*1+8*0
```

- 二维数组：矩阵积

  - A的第一行与B的第一列，对应元素的乘积之和，构成了新向量C的第一行第一列，坐标为(0,0)的元素。
  - A的第一行与B的第二列，对应元素的乘积之和，构成了新向量C的第一行第二列，坐标为(0,1)的元素。
  - A的第二行与B的第一列，对应元素的乘积之和，构成了新向量C的第二行第一列，坐标为(1,0)的元素。
  - 总结来看，新向量元素的坐标，y值取决于A向量所处的行，x值取决于B向量所处的列。而每个元素的计算，总是A的行元素与B的列元素的点积。
 
 (所得到的数组中的每个元素为，第一个矩阵中与该元素行号相同的元素与第二个矩阵与该元素列号相同的元素，两两相乘后再求和)

```python
A = [[1, 2],[3,7]]
B = [[4, 3],[5, 0]]
print('A与B的点积为:\n',np.dot(A,B))
```

```
#A:[1,2]  B:[4,3] =>1*4+2*10=14(第0行*第0列加和);  1*3+2*0=3(第0行*第1列加和)
#  [3,7]    [5,0] =>3*4+7*5=47(第1行*第0列加和);   3*3+7*0=9(第1行*第1列加和)
A与B的点积为:
 [[14  3] 
 [47  9]]
```

dot()函数可以通过numpy库调用，也可以由数组实例对象进行调用=>a.dot(b) 与 np.dot(a,b)结果相同

矩阵积计算不遵循交换律：np.dot(a,b) 和 np.dot(b,a) 结果不同

```python
a = np.array([[1,2,3], [4,5,6]], dtype=np.float64) # we can specify dtype
b = np.array([[7,8], [9,10], [11, 12]], dtype=np.float64)
print (a.dot(b))

#output
#[[ 58.  64.]
# [139. 154.]]
```

## Sum across a dimension 维度求和

```python
x = np.array([[1,2],[3,4]])
print (x)
print ("sum all: ", np.sum(x)) # adds all elements
print ("sum by col: ", np.sum(x, axis=0)) # add numbers in each column
print ("sum by row: ", np.sum(x, axis=1)) # add numbers in each row

#output
#[[1 2]
# [3 4]]
#sum all:  10
#sum by col:  [4 6]
#sum by row:  [3 7]
```

## Transposing 转置

```python
x = np.array([[1,2],[3,4]])
print ("x:\n", x)
print ("x.T:\n", x.T)
```

```
x:
 [[1 2]
 [3 4]]
x.T:
 [[1 3]
 [2 4]]
```
