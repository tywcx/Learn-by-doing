# 列表 list

list是一种有序的集合，可以随时添加和删除其中的元素。

## 按顺序计数时，是从0开始计数

input:

```python
print(list(range(10)))    # range表示一个区间，数字10表示输出10个数字
print(list(range(1,10)))  # (1,10)表示输出第2个数到第10个数
```

output:

```python
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
[1, 2, 3, 4, 5, 6, 7, 8, 9]
```


input:

```python
list('iamestelle')
```

output:

```
['i', 'a', 'm', 'e', 's', 't', 'e', 'l', 'l', 'e']
```


## 常用函数

#### 长度：len（）

input:

```python
l = ['aa', 'bb', 'cc']
len(l)
# output:3
```

用索引来访问list中每一个位置的元素：

```python
print(l[0]) # 访问第一位置的元素
print(l[1]) # 访问第二位置的元素
print(l[2]) # 访问第三位置的元素

# output:
# aa
# bb
# cc
```

**可以倒着来访问**

```python
print(l[-1]) # 访问倒数第一位置的元素
print(l[-2]) # 访问倒数第二位置的元素
print(l[-3]) # 访问倒数第三位置的元素

# output:
# cc
# bb
# aa
```

**可以访问一个区间**

```python
print(l[:])   # 冒号:左起始、右终止
print(l[1:])  # 左：1 -- 表示从第二个元素开始取
print(l[:-2]) # 右：-2 -- 表示取到倒数第三个元素停止

# ['aa', 'bb', 'cc']
# ['bb', 'cc']
# ['aa']
```

#### 修改元素

直接修改指定位置元素：


```python
l[0] = 'dd'
print(l)
# ['dd', 'bb', 'cc']
```



#### 添加元素

list是一个可变的有序表，所以，可以往list中追加元素到末尾：

```python
l.append('ee') # append直接在list最后继续添加元素
print(l)

l.insert(1,'ff') # insert在指定位置添加元素
print(l)

# ['dd', 'bb', 'cc', 'ee']
# ['dd', 'ff', 'bb', 'cc', 'ee'] 
```

**insert 是在指定位置插入新元素，不是修改指定位置元素**

#### 删除元素

```python
l.pop()   # pop直接删除最后一个元素
print(l)

a.pop(0)  # pop也可以指定元素位置，数字0为第一个元素
print(l)

# ['dd', 'ff', 'bb', 'cc']
# ['ff', 'bb', 'cc']
```

#### list里面的元素的数据类型也可以不同

```python
L = ['Apple', 123, True]
```

#### list元素也可包含另一个list

```python
s = ['python', 'java', ['asp', 'php'], 'c++']
```

**len(s)=4，s只有4个元素，其中s[2]又是一个list**

- p = ['asp', 'php']
- s = ['python', 'java', p, 'c++']

要取到'php'：用p[1]或者s[2][1]

#### list可为空

list中一个元素也没有，就是一个空的list，它的长度为0
