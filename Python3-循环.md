# for 循环

**for ... in ...** in后面，跟随的是一个区间，是要循环的内容。

```python
#1-100:i能整除10的数字加和
sum=0   
for i in range(1,101): #**[1,101); range(101)=>[0,101)**
    if i%10==0:
        sum=sum+i
        print(i)
print(sum)
for i in range(10):
    print(i)
```

**range也是左闭右开**

run一下，output：

```
10
20
30
40
50
60
70
80
90
100
550
```


**用for循环出list的内容：

```python
pl = ['aa', 'bb', 'cc']
for i in pl:
    print(i)
    
# aa
# bb
# cc
```
