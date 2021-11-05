# 数据类型 DataFrame

一种表格形型的数据结构，类似excel的sheet，是数据挖掘中最常用的一个工具。

每列可以是不同的值类型(数值、字符串、布尔型等)，DataFrame即有行索引也有列索引

## 创建DataFrame

```python
import pandas as pd 
df = pd.DataFrame({'aa':[1,2,3], 'bb':[4,5,6], 'cc':[7,8,9]})
print(df)
```

```
   aa  bb  cc
0   1   4   7
1   2   5   8
2   3   6   9
```

创建一个3行3列的df表格：\"aa/bb/cc\"是列名，最左列\"0/1/2\"是index索引（0:第一行，以此类推）。

## 列操作

#### 获取列（column）

```python
print('第一种方法--取aa列：')
col = df['aa']  # 注意在列名上加引号
print(col) 
print('-------------------')
print('第二种方法--取aa列：')
col = df.aa
print(col)
```

```
第一种方法--取aa列：
0    1
1    2
2    3
Name: aa, dtype: int64  ## print(col) :输出aa列的值。dtype: 表示这列的数据格式是int。
-------------------
第二种方法--取aa列：
0    1
1    2
2    3
Name: aa, dtype: int64
```

#### 添加列

```
df['dd']=[11,22,33]
print(df)
```

```
   aa  bb  cc  dd
0   1   4   7  11
1   2   5   8  22
2   3   6   9  33
```

### 删除列

```
df.pop('dd')
print(df)
```


```
   aa  bb  cc
0   1   4   7
1   2   5   8
2   3   6   9

```

### 删修改

```
df['aa']=[11,22,33]
print(df)
```

```
   aa  bb  cc
0  11   4   7
1  22   5   8
2  33   6   9
```

## 行操作

### 获取行

用索引取行：**左闭右开**

```python
print('取第一行')
line = df[:1]
print(line)
print('-------------------')
print('取第一行')
line = df[0:1]
print(line)
print('-------------------')
print('取前两行')
line = df[:2]
print(line)
print('-------------------')
print('取所有的行')
line = df[:]
print(line)
print('-------------------')
print('取倒数第一行')
line = df[-1:]
```

```
取第一行
   aa  bb  cc
0  11   4   7
-------------------
取第一行
   aa  bb  cc
0  11   4   7
-------------------
取前两行
   aa  bb  cc
0  11   4   7
1  22   5   8
-------------------
取所有的行
   aa  bb  cc
0  11   4   7
1  22   5   8
2  33   6   9
-------------------
取倒数第一行
   aa  bb  cc
2  33   6   9
```

## 取对象

```python
print('取bb列第二个对象：',df['bb'][1])
print('替换该数值：50')
df['bb'][1]=50
print('替换后取bb列第二个对象：',df['bb'][1])
```

```
取bb列第二个对象： 5
替换该数值：50
替换后取bb列第二个对象： 50
```

## 合并操作

### 行连接 - concat 纵向连接：纵向变长
 
```python
df1=pd.DataFrame({'key':['a','b','c'],'value':[1,2,3]})  
print(df1)
print('---------------------')
df2=pd.DataFrame({'key':['d','e','f'],'value':[4,5,6]}) 
print(df2)
print('---------------------')
df3=pd.concat([df1,df2])
print(df3)
```

```
key  value
0   a      1
1   b      2
2   c      3
---------------------
  key  value
0   d      4
1   e      5
2   f      6
---------------------
  key  value
0   a      1
1   b      2
2   c      3
0   d      4
1   e      5
2   f      6
```

### 列连接 - merge 横向连接：横向变宽

```python
df1=pd.DataFrame({'key':['a','b','c'],'value1':[1,2,3]})
print(df1)
print('---------------------')
df2=pd.DataFrame({'key':['a','b','c'],'value2':[4,5,6]}) 
print(df2)
print('---------------------')
df3=pd.merge(df1,df2)
print(df3)
```

```
  key  value1
0   a       1
1   b       2
2   c       3
---------------------
  key  value2
0   a       4
1   b       5
2   c       6
---------------------
  key  value1  value2
0   a       1       4
1   b       2       5
2   c       3       6
```

