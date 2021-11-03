# 数据类型

Python中，数据类型有以下几种：

## 数字

- 整数 int：

  Python可以使用```_```分割数字中间的多个0: 10000000000=10_000_000_000

- 浮点数 float：用科学计数法表示，把10用e替代，如1.23e9，或0.000012可以写成1.2e-5。

## 字符串

#### 字符串 string

单引号、双引号均可：'abc'，"abc"

字符串“相加”：print('hello'+' the fucking world!')=>hello the fucking world!

#### 转义字符：```\n```

  print("I'm OK!")=>I'm OK! #使用双引号，字符串中的单引号无需使用转义字符
  print('I\'m "OK!!"')=>I'm "OK!!" #使用单引号：字符串中的单引号（I\'m ）需要转义字符，双引号无需
  print("I'm \"OK\"!!!")=>I'm "OK"!!! #同上
  
其他转义字符：如

- ```\n``` 表示换行
- ```\t``` 表示tab
- ```\\``` 表示```\``` 斜杠本身

#### Tips：
- 字符串中需要使用多个```\```转义，Python可使用```r''```表示''内部的字符串默认不转义：

  print(r'''hello,\nworld''')=>hello,\nworld
  print(r'''hello,\nworld''')=>hello,
                               world
  
- 字符串中有多个换行，需要使用多个```\n``` 表示换行，Python可使用```''' '''```表示多行内容：
  
## 空值：一般用```None``` 表示

## 变量

变量名必须是大小写英文、数字和_的组合，且不能用数字开头。
Python程序是大小写敏感的！

在Python中，可以把任意数据类型赋值给同一个变量

## 判断逻辑

#### 布尔值 bool

- True
- False

布尔表达式返回的True和False，不是字符串string

**type( )**可以用来查询变量的格式：

```
print(type(True))
print(type('True'))
```

=>
<class 'bool'>
<class 'str'>

第一个是布尔表达式返回的True，不带引号；
第二个是字符串string返回的格式str (string), 带引号。

## 常量

常量名通常用大写。如PI


## 转换成整数

- int( )
- round( )

输入：

```python
print(3.5/2)		# 直接除法，有小数点
print(int(3.5/2))   # 直接取整数部分
print(round(3.5/2)) # 进行四舍五入取整
print(int('4'))     # 将字符串转换成整数，字符串引号内需要本身就是整数
```

run一下，输出：

```
1.75
1
2
4	 
```


## 转换成浮点数

- float( )
- round( )

输入：

```python
print(4/2)                    # 答案直接是整数，只取一位小数
print(float(3.17/2))          # 答案为有限位小数，直到输出完整答案为止
print(float('3.5'))           # 将字符串转换成浮点数，字符串引号内为数字
print(round(0.123456,4))      # round可控制浮点数精度，第二个参数‘4’为保留4位小数
```

run一下，输出：

```
2.0
1.585
3.5
0.1235
```

## 转换成字符串

- str( )

输入：

```python
print(str(4.5))
print(str(5))
print(str(True))
```

run一下，输出：

```
4.5   # 这些数字已经变成字符串类型
5
True
```

## 转换成布尔值

- bool( )

输入：

```python
print(bool(10))              # 任何非零数字判断为 True
print(bool(0))               # 数字零判断为 False
print(bool(3.9))             # 非零数字判断为 True
print(bool(''))              # 空字符串判断为 False
print(bool(None))            # None 空值判断为 False
print(bool('Girls-In-AI'))   # 任何非空字符串判断为 True
```

run一下，输出：

```
True
False
True
False
False
True
```



## 检查数据类型

- type( )


输入：

```python
a = str(False)  # 将bool值转换成字符串，并赋值给变量 a
print(bool(a))  # a 为非空字符串，用bool转换后，判断为 True
```

run一下，输出：

```
True
```
