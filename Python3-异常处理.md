# 异常处理 Try/Except

```python
user_input=input('please enter a number:')
try:
    user_input=int(user_input)
    print(user_input)
    user_input=user_input+1
    print('now the number is %d' % user_input)
except:
    print('please check, you enter a wrong type')
```

```
#input 5

#output: 
please enter a number:5
now the number is 6
```

- try里面任何一步错误，都会直接执行except：

  - 输入类型错误：
  
  ```
  #input cs

  #output: please enter a number:please check, you enter a wrong type
  ```
  
  - 出现语法错误语句：print('the number is %d' ```+``` user_input)，则会输出：
  
  ```
  #input 5

  #output:
  please enter a number:5
  please check, you enter a wrong type
  ```

**不一定是用户输入错误，也有可能是代码本身错误**
