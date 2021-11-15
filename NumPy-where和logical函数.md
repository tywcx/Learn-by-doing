## np.where和np.logical_and/or/not

#### np.where()

np.where(condition)，若条件满足，返回索引值

np.where(condition，x，y)，若条件满足，返回x，否则返回y

主要是运用在一维数组、二维数组、多维数组和根据元素找到对应的索引位置：

- 一维数组中直接返回索引位置，但是是以数组的形式返回的，默认为int
- 二维数组中返回两组索引(分别是行纵坐标的索引)
- 多维数组中对应True类型的位置返回，其它的根据设定的值进行输出
- 可根据元素的bool值，直接找到数组中对应的True的位置，然后通过np.where直接找到对应的行纵坐标。

```python
import numpy as np

# 1d - 一维数组
a = np.arange(2,8)
b = np.where(a>4) # 返回索引值
c = np.where(a>4, a, 0) # 满足条件，返回a，否则返回0
print(a)  # >>> [2 3 4 5 6 7]
print(b)  # >>> (array([3, 4, 5]),)
print(c)  # >>> [0 0 0 5 6 7]

# 2d - 二维数组
aa = np.arange(3*4).reshape(3,4)
bb = np.where(aa>5) # 返回两组索引(分别是行纵坐标的索引)
cc = np.where(aa>5,aa,0)
print(aa)   
print(bb)  
print(cc)   
#[[ 0  1  2  3]
# [ 4  5  6  7]
# [ 8  9 10 11]]
#(array([1, 1, 2, 2, 2, 2]), array([2, 3, 0, 1, 2, 3])) # 第一行第二列：6，以此类推
#[[ 0  0  0  0]
# [ 0  0  6  7]
# [ 8  9 10 11]]

# multi d - 多维数组
m = np.arange(16).reshape(2,2,4)
n = np.where([True,False,True,False],m,0)
print(m)
print(n)
#[[[ 0  1  2  3]
#  [ 4  5  6  7]]

# [[ 8  9 10 11]
#  [12 13 14 15]]]
#[[[ 0  0  2  0]  # 第0行第0列：True，输出m；第0行第1列：False，输出0；以此类推
#  [ 4  0  6  0]]

# [[ 8  0 10  0]
#  [12  0 14  0]]]

#find position
x = np.arange(4*5).reshape(4,5)
position=[5,9,15]
y = np.isin(x,position)
z = np.where(y)
print(x)
print(y)
print(z)
#[[ 0  1  2  3  4]
# [ 5  6  7  8  9]
# [10 11 12 13 14]
# [15 16 17 18 19]]
#[[False False False False False] #position=[5,9,15]为True，否则为False
# [ True False False False  True]
# [False False False False False]
# [ True False False False False]]
#(array([1, 1, 3]), array([0, 4, 0])) #通过np.where直接找到对应的行纵坐标

```

#### np.logical_and/or/not()

**np.logical_and (逻辑与)**

```python
import numpy as np
a=np.logical_and(True,False)
print(a)

a=np.logical_and([True,False],[False,False])
print(a)

a=np.arange(5)
print(a)
print(np.logical_and(a>1,a<4))
```

```
#output
False
[False False]
[0 1 2 3 4]
[False False  True  True False]
```


**np.logical_or (逻辑或)**

```python
import numpy as np
b=np.logical_or(True,False)
print(b)

b=np.logical_or([True,False],[False,False])
print(b)

b=np.arange(5)
print(b)
print(np.logical_or(b>1,b<3))
```

```
#output
True
[ True False]
[0 1 2 3 4]
[ True False False False  True]
```

**np.logical_not (逻辑非)**

```python
import numpy as np
c=np.logical_not(3)
print(c)

c=np.logical_not([True,False,0,1])
print(c)

b=np.arange(5)
print(c)
print(np.logical_not(c<3))
```

```
#output
False
[False  True  True False]
[False  True  True False]
[False False False False]
```
