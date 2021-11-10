# 拼接Numpy数组的不同方式

**拼接方法介绍**

- numpy.append(arr, values, axis=None)
- numpy.concatenate((a1, a2, ...), axis=0, out=None)
- stack(), hstack(), vstack()
- np.r_ , np.c_

## numpy.append(arr, values, axis=None)

可以拼接：
- 一个数组和一个数值
- 两个数组

**但三个及以上数组不能直接append拼接**

```python
import numpy as np
a = np.arange(4)      
b = np.arange(4,8)    
print(a)  # >>>[0 1 2 3]
print(b)  # >>>[4 5 6 7]

# 拼接一个数组和一个数值
c=np.append(a,4)
print(c)  # >>>[0 1 2 3 4]

#拼接两个数组：输出为一维数组
c=np.append(a,b)
print(c)  # >>>[0 1 2 3 4 5 6 7]

#拼接列表为数组（一维）
c=np.append([1,2,3], [[4,5,6],[7,8,9]])
print(c)  # >>>[1 2 3 4 5 6 7 8 9]

#不同坐标抽方向的拼接 （二维数组拼接->二维数组）
c=np.append([[1,2,3],[4,5,6]], [[7,8,9]], axis=0) # axis=0 行拼接：纵向加长
print(c) 
# [[1 2 3]
#  [4 5 6]
#  [7 8 9]]

#二维数组同 （二维数组拼接->二维数组）
a=np.array([[1,2],[3,4]])
b=np.array([[5,6],[7,8]])
print(a)
#[[1 2]
# [3 4]]
print(b)
#[[5 6]
# [7 8]]

c=np.append(a,b,axis=0) # axis=0 行拼接：纵向加长
print(c)
#[[1 2]
# [3 4]
# [5 6]
# [7 8]]

c=np.append(a,b,axis=1) # axis=1 列拼接：横向加长
print(c)
#[[1 2 5 6]
# [3 4 7 8]]
```

## numpy.concatenate((a1, a2, …), axis=0, out=None)

- a1,a2,…: 数组类型的参数，传入的数组必须具有相同的形状
- axis: 指定拼接的方向，默认axis = 0（逐行拼接,纵向加长）；axis= 1（纵向拼接，横向加长）
- axis=None，则数组会被展开为一维

concatenate()比append()效率更高，适合大规模的数据拼接，能够一次完成多个数组的拼接

```python
import numpy as np
a=np.array([[1,2],[3,4]])
b=np.array([[5,6],[7,8]])
print(a)
#[[1 2]
# [3 4]]
print(b)
#[[5 6]
# [7 8]]

c=np.concatenate((a,b), axis=0) # axis=0 行拼接：纵向加长
print(c)
#[[1 2]
# [3 4]
# [5 6]
# [7 8]]

c=np.concatenate((a,b), axis=1) # axis=1 列拼接：横向加长
print(c)
#c=np.concatenate((a,b.T), axis=1)
#print(c)
#[[1 2 5 6]
# [3 4 7 8]]

c=np.concatenate((a,b), axis=None)  #axis=None: 一维
print(c)  # >>>[1 2 3 4 5 6 7 8]
```

## stack(), hstack(), vstack()

在一个新的轴方向上堆叠数组:
- vstack() 在竖直方向堆叠
- hstack() 在水平方向堆叠

```python
import numpy as np

a=np.array([1,2,3,4])
b=np.array([5,6,7,8])
c=np.stack((a,b))  # 默认np.stack((a,b),axis=0) 注意 np.stack(a,b)单括号 会报错
print(c)  # axis=0 行拼接
#[[1 2 3 4]
# [5 6 7 8]]

c=np.vstack((a,b))  # 行拼接：纵向加长
print(c)
#[[1 2 3 4]
# [5 6 7 8]]

c=np.hstack((a,b)) #列拼接：横向加长
print(c)  # >>>[1 2 3 4 5 6 7 8]

c=np.stack((a,b),axis=-1) # axis=0 行拼接
#c=np.stack((a,b),axis=1) 
print(c)
#[[1 5]
# [2 6]
# [3 7]
# [4 8]]

c=np.stack(([1,2,3],[4,5,6]),axis=0)
print(c)
#[[1 2 3]
# [4 5 6]]
```

##  np.r_ 和 np.c_

以索引的方式拼接数组

```python
import numpy as np
a=np.array([[1,2],[3,4]])
b=np.array([[5,6],[7,8]])
c=np.r_[a,b] # 与np.concatenate((a,b), axis=0) 和 np.vstack((a,b)) 等价
print(c)  #行拼接
#[[1 2]
# [3 4]
# [5 6]
# [7 8]]
 
c=np.c_[a,b] # 与np.concatenate((a,b), axis=1) 和 np.hstack((a,b)) 等价
print(c)  #列拼接
#[[1 2 5 6]
# [3 4 7 8]]

#还可以使用字符串描述拼接方式
c=np.r_['-1',a,a] #最后的一个轴方向拼接
print(c)
#[[1 2 1 2]
# [3 4 3 4]]

c=np.r_['0,2',[1,2,3],[4,5,6]] #第一个轴方向拼接，与stack(([1,2,3],[4,5,6], axis=0)) 等价
print(c)  # 行拼接
# [[1 2 3]
 [4 5 6]]

c=np.r_['0,2,0',[1,2,3],[4,5,6]] 
print(c)
#[[1]
# [2]
# [3]
# [4]
# [5]
# [6]]

c=np.r_['1,2,0',[1,2,3],[4,5,6]]  # 与stack(([1,2,3],[4,5,6], axis=1)) 等价
print(c)  #列拼接
#[[1 4]
# [2 5]
# [3 6]]

```

## 总结
- 将两个一维数组拼接成一个更长的一维数组：（列拼接：横向加长）
  - Input:
  ```
  a = np.array([1, 2, 3])
  b = np.array([4, 5, 6])
  ```
  - Output:
  ```
  [1 2 3 4 5 6]
  ```
  - 拼接的方法有：
    - np.append(a, b)
    - np.concatenate((a, b))
    - np.hstack((a, b))
    - np.r_[a, b], np.r_['0', a, b], np.r_['-1', a, b]

- 将两个一维数组拼接成二维数组：
  - Input:
  ```
  a = np.array([1, 2, 3])
  b = np.array([4, 5, 6])
  ```
  - Output 1:
  ```
  [[1 2 3]
   [4 5 6]]
  ```
  - 拼接的方法有：
    - np.vstack((a, b))
    - np.stack((a, b), axis=0)
    - np.r_['0,2', a, b]
  
  - Output 2:
  ```
  [[1 4]
   [2 5]
   [3 6]]
  ```
  - 拼接的方法有：
    - np.stack((a, b), axis=1)
    - np.c_[a, b]
    - np.r_['1,2,0', a, b]

- 拼接两个二维数组
  - 水平拼接（横向加长）:
    - np.append(m, n, axis=1)
    - np.c_[m, n]
    - np.concatenate((m, n), axis=1)
    - np.hstack((m, n))
  - 竖直拼接（逐行拼接，纵向加长）:
    - np.r_[m, n]
    - np.append(m, n, axis=0)
    - np.concatenate((m, n))
    - np.vstack((m, n))
