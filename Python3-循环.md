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

# while 循环

## break & continue

通常和if配合使用

- break：退出while循环
- continue：退出本次循环


'''python
while True:
    user_iput=input()
    if user_iput[0] == '#':    #条件1
        print('#, in while')
        continue
    if user_iput == 'stop':    #条件2
        print('wanna stop')
        break
    print(user_iput)           
print('out of while')
```


ipput **input()返回的数据格式都是字符串！**


```
#how are you      #满足条件1，continue
fine, 3Q, and you? #不满足两个if，直接print
#fine               #满足条件1，continue
stop                 #满足条件2，break，跳出while循环
```



output


```
#, in while
fine, 3Q, and you?
#, in while
wanna stop
out of while
```

