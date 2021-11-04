# 字典 dict

dict：dictionary，在其他语言中也称为map，使用键-值**dict = {key1: value1, key2: value2, ...}**存储：

- key是唯一索引，不在一个dict里重复出现
- dict是无序的，不能按照位置来查找

**区别 list & dict

list是中括号[]，那么在dict使用的符号就是大括号{}

根据同学的名字查找对应的成绩，如果用两个list实现：

names = ['aa', 'bb', 'cc']
scores = [90, 80, 70]

## 新建 dict


```python
d = {'aa': 90, 'bb': 80, 'cc': 70}
```


## 查找/替换 value

- 查找

```python
d['aa']    # 按照key查找对应的value
# output: 90
```

- 替换

```python
d['aa'] = 60  # 直接给key赋值，进行值的替换
d['aa']       #此时输出最新赋值的分数
```

```python
d = {'aa': 90, 'bb': 80, 'cc': 80}  
print(d['aa'])                     
d['aa']=60
print(d['aa'])
```

```
90
60
```

- 判断字典中是否存在某key：两种方法

  - 'key' in dict：通过in判断key是否存在

  ```python
  print('dd' in d, 'cc' in d) # 判断“cc”和“dd”是否在字典里
  
  # output: False True
  ```


  - d.get('key', 'return') ：通过dict提供的get()方法
  - d.get('key')，return None ：如果key不存在，可以返回None，或者自己指定的value

  ```python
  print(d.get('dd', '查无此人'))
  # output: '查无此人'
  ```


## 添加 key-value

```python
d['dd'] = 100    # 直接添加 dd 和 其分数
print(d)           # print出来的是d中所有人的分数

# {'aa': 90, 'bb': 80, 'cc': 80, 'dd': 100}
```


## 删除 key-value

```python
d.pop('dd')    # 直接用pop(key)删除
print(d)

# {'aa': 90, 'bb': 80, 'cc': 80}  
```

## list VS dict：

- dict：
  - 查找和插入的速度极快，不会随着key的增加而变慢
  - 需要占用大量的内存，内存浪费多

- list：
  - 查找和插入的时间随着元素的增加而增加
  - 占用空间小，浪费内存很少。

**所以，dict是用空间来换取时间的一种方法**

**dict的key必须是不可变对象：在Python中，字符串、整数等都是不可变的，可以作为key。而list是可变的，就不能作为key**


