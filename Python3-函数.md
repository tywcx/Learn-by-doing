# 函数 function

Python内置很多函数，可以直接调用。

## python内置函数


```python
print(max(1,2,3,4))
print(max([1,2,3,4]))  # max() 里面可以是一串数字，也可以是一个list

print(abs(-1.23))
print(list(range(5))) #返回一个区间

#4
#4
#1.23
#[0, 1, 2, 3, 4]
```


## 自定义函数

- def 函数名（参数）
- 函数体
- 返回结果

```python
def add(x,y):   # add为函数名，x,y为参数
    return x+y  # x+y 为映射关系

add(100,1)  # 调用函数
# 101
```


## 调用函数

函数名(参数)

返回结果


[Girls-In-AI](https://github.com/girls-in-ai/Girls-In-AI#girls-in-ai)
```python
def GIA(heart):  # 这个heart是参数，是一个字符串的参数
    print('\n'.join([''.join([(heart[(x-y)%len(heart)]if((x*0.05)**2+(y*0.1)**2-1)**3-(x*0.05)**2*(y*0.1)**3<=0 else' ')for x in range(-30,30)])for y in range(15,-15,-1)]))

GIA('GirlsRunTheWorld') # 赋值为 'GirlsRunTheWorld'
                        # 赋值时，请记得加引号
```

output：

```
                                                          
                                                            
                unTheWorl           eWorldGir               
            lsRunTheWorldGirl   nTheWorldGirlsRun           
          rlsRunTheWorldGirlsRunTheWorldGirlsRunThe         
         rlsRunTheWorldGirlsRunTheWorldGirlsRunTheWo        
        rlsRunTheWorldGirlsRunTheWorldGirlsRunTheWorl       
        lsRunTheWorldGirlsRunTheWorldGirlsRunTheWorld       
        sRunTheWorldGirlsRunTheWorldGirlsRunTheWorldG       
        RunTheWorldGirlsRunTheWorldGirlsRunTheWorldGi       
        unTheWorldGirlsRunTheWorldGirlsRunTheWorldGir       
        nTheWorldGirlsRunTheWorldGirlsRunTheWorldGirl       
         heWorldGirlsRunTheWorldGirlsRunTheWorldGirl        
          WorldGirlsRunTheWorldGirlsRunTheWorldGirl         
          orldGirlsRunTheWorldGirlsRunTheWorldGirls         
            dGirlsRunTheWorldGirlsRunTheWorldGirl           
             irlsRunTheWorldGirlsRunTheWorldGirl            
              lsRunTheWorldGirlsRunTheWorldGirl             
                unTheWorldGirlsRunTheWorldGir               
                  heWorldGirlsRunTheWorldGi                 
                    orldGirlsRunTheWorldG                   
                       GirlsRunTheWorl                      
                          sRunTheWo                         
                             The                            
                              e                          
```


