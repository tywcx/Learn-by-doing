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

```

## numpy.concatenate((a1, a2, …), axis=0, out=None)

- a1,a2,…: 数组类型的参数，传入的数组必须具有相同的形状
- axis: 指定拼接的方向，默认axis = 0（逐行拼接,纵向加长）；axis= 1（纵向拼接，横向加长）
- axis=None，则数组会被展开为一维

concatenate()比append()效率更高，适合大规模的数据拼接，能够一次完成多个数组的拼接



总结
将两个一维数组拼接成一个更长的一维数组：
将两个一维数组拼接成二维数组：
拼接两个二维数组
