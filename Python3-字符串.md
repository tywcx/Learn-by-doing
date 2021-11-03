# 字符串 String

#### **字符串不可改变**

即字符串里的每一个字符都不可以被替代

## 字符串常用函数 
#### 字符串长度：len( ) 

#### 分割字符串：

利用‘找字符’的方法‘[ ]’ ：可以找单独一个字符，也可以提取部分字符串


```
name='estelle'
print(name[len(name)-1],name[len(name)-3:len(name)],phone[len(name)-3:len(name)-1])
```

=>e lle ll

提取字符串最后一位字符：[len-1]

提取最后三个字符：[len-3:len]

注意**左闭右开**

#### 用’in‘ 找字符 

in 是一个布尔运算符，可以比较两个字符串，所以返回值是true/false:

```
print(name[len(name)-1],name[len(name)-3:len(name)],name[len(name)-3:len(name)-1])
single='s'
print(single in name)
print(name in single)
```

=>
True

False

#### 其它方法method:

方法method vs 函数function: 

len(phone) — function (method是使用句点作为分割，在变量名后跟上方法名)

phone.upper() — method   (function括号里面加上变量名)

- upper/lower/find (大/小写/查找)
- strip （跳过前后空格）
- startswith （判断首位字符是否以xx开始）：print(name.startswith('e'),name.startswith('s'))
- string.split(seperator, maxsplit) 字符串切割
- join 连接字符串

#### 格式操作符

- %d —— 格式化整数
- %g —— 格式化浮点数
- %s —— 格式化字符串  

- 百分号%对int这个数据格式而言，是模运算符； 但对字符串而言，%是格式操作符   

```
name='bob'
word ='estelle, is, a genius'
names=('adam','bob','cc')
print('my name is %s' % name +', you can say: %s' % word + 'bob has %d apples and %g oranges' % (2, 2.5))
print(word.split(), word.split(','), word.split(',',1), word.split(',',2))
print('#'.join(names), '&'.join(names))
```

=>
```
my name is bob, you can say: estelle, is, a geniusbob has 2 apples and 2.5 oranges
['estelle,', 'is,', 'a', 'genius'] ['estelle', ' is', ' a genius'] ['estelle', ' is, a genius'] ['estelle', ' is', ' a genius']
adam#bob#cc adam&bob&cc
```
