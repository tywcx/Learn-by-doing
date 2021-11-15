## 对Numpy数组元素的复制操作

方法有：

- np.tile()：以axis为最小单位(axis-wise)进行复制 - 复制的是多维数组本身
- np.repeat()：以element为最小单位(element-wise)进行复制的 - 复制的是多维数组的每一个元素

#### np.tile(A,reps)

tile函数两个作用：①扩充数组元素 ②提升数组维度

- 输入: A是数组, reps是个list,reps的元素表示对A的各个axis进行复制的次数：即根据reps中元素扩充数组A中对应轴上的元素
- 返回: 一个数组, 维度的数量等于max(A.ndim,len(reps)), **注意不要混淆A.ndim和A.shape**
- 输入: A是数组, reps是个list,reps的元素表示对A的各个axis进行复制的次数：即根据reps中元素扩充数组A中对应轴上的元素
  - A.ndim == len(reps)：
    - 如对一维数组，整体数组复制reps次；对二维数组，数组各轴上的元素依次重复reps序列中元素对应的次数
  - A.ndim > len(reps)：则需增加list的长度, 使得 A.ndim = len(reps)
    - 即在reps序列的索引为0的位置开始添加元素1，直到reps的长度和数组的维度数相等，然后数组各轴上的元素依次重复reps序列中元素对应的次数。如原来的list是[2,2],增加长度后是[1,2,2]
  - A.ndim < len(reps)：则需调整A的维度使得 A.ndim = len(reps)
    - 即添加长度为1的维度。注意:新的维度在原维度的前面, 如原来的A.shape是(3,5),调整后是(1,3,5);A.shape(3,)=> a.shape(1,1,3)(直到reps的长度和数组的维度数相等。)

  **总结：即少的一方从最开始的位置添加1，直至两者相等：A.ndim == len(reps)**
  
```python
import numpy as np

a=np.array([1,2,3])

#Case 1:a.ndim == len(reps)，reps为整数2 => 即将数组a在axis=0方向上复制2次
print(np.tile(a,2))
# >>>> [1 2 3 1 2 3]

#Case 2: a.ndim < len(reps) => 1.调整a的维度：a.shape(3,)=> a.shape(1,3)；2.axis=0上复制2次，axis=1上复制2次(np.tile(a,(2,2)))
print(np.tile(a,(2,2)))
#[[1 2 3 1 2 3]
# [1 2 3 1 2 3]]

#Case 3: a.ndim < len(reps) => 1.调整a的维度：a.shape(3,)=> a.shape(1,1,3)；2.axis=0上复制2次，axis=1上复制1次，axis=1上复制2次
print(np.tile(a,(2,1,2)))
#[[[1 2 3 1 2 3]]

# [[1 2 3 1 2 3]]]

b=np.array([[1,2], [3,4]])

#Case 4:b.ndim > len(reps) => 1.调整reps=[2]=> [1,2]；2.axis=0上复制1次，axis=1上复制2次
print(np.tile(b,2))
#[[1 2 1 2]
# [3 4 3 4]]

#Case 5:b.ndim == len(reps)，reps为整数2 => 即将数组b在axis=0上复制2次，axis=1上复制21
print(np.tile(b,(2,1)))
#[[1 2]
# [3 4]
# [1 2]
# [3 4]]

c=np.array([1,2,3,4])
#Case 6: c.ndim < len(reps) => 1.调整c的维度：a.shape(4,)=> a.shape(1,4)（一维变二维）；2.axis=0上复制4次，axis=1上复制1次(np.tile(c,(4,1)))
print(np.tile(c,(4,1)))
#[[1 2 3 4]
# [1 2 3 4]
# [1 2 3 4]
# [1 2 3 4]]
```


#### np.repeat(a, repeats, axis=None)

repeat函数的作用：①扩充数组元素 ②降低数组维度

numpy.repeat(a, repeats, axis=None)：若axis=None，对于多维数组而言，可以将多维数组变化为一维数组，然后再根据repeats参数扩充数组元素；若axis=M，表示数组在轴M上扩充数组元素。


返回: 

- 输入: 输入: a是数组,repeats是各个元素复制的次数,在axis的方向上进行复制
- 返回: 如果不指定axis,则将复制后的结果展平(维度为1)后返回;如果指定axis,则不展平：
  - 即若axis=None，对于多维数组而言，可以将多维数组变化为一维数组，然后再根据repeats参数扩充数组元素；
  - 若axis=M，表示数组在轴M上扩充数组元素（M=-1代表最后一条轴）。

```python
import numpy as np

a=np.array([1,2,3])

#Case 1:数组a复制4次（没有指定axis，返回结果为一维数组）
print(np.repeat(a,4))
#[1 1 1 1 2 2 2 2 3 3 3 3]

b=np.array([[1,2], [3,4]])

#Case 2:数组b各个元素复制2次（没有指定axis，返回结果为一维数组）
print(np.repeat(b,2))
#[1 1 2 2 3 3 4 4]

#Case 3:数组b在axis=1上每个元素复制3次（返回结果仍为二维数组）
print(np.repeat(b,3,axis=1))
#[[1 1 1 2 2 2]
# [3 3 3 4 4 4]]

#Case 4:数组b在axis=0上复制：将axis=0方向上的第0个元素复制1次，第1个元素复制2次
print(np.repeat(b,[1,2],axis=0))
#[[1 2]
# [3 4]
# [3 4]]

```
