
# 条件判断 if

```
age=input()
x=int(age)
if x>=16 :
    if x<18:
        print('your age is %d'% x)
        print('now you are an audlt, and you can go to work')
    elif x<=20:
        print('but you cannot marry')
    else:
        print('your age is %d'% x)
        print('you are totally an audlt, and you can marry!')
else:
    print('your age is %d'% x)
    print('now you are still a teenager, you cannot go to work')
```

```
input
21

output
your age is 21
you are totally an audlt, and you can marry!
```


使用input()读取输入：

**因为input()返回的数据类型是str，str不能直接和整数比较，必须先把str转换成整数。Python提供了int()函数来完成这件事情**

否则会报错如下：

`
TypeError: '>=' not supported between instances of 'str' and 'int'
`

