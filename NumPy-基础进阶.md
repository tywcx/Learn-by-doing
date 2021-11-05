# NumPy 基础进阶


#### Slicing 切片
  
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
 ···
