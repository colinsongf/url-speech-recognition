1. [numpy中的范数计算方法 linalg.norm](https://zhuanlan.zhihu.com/p/33217726 )
2. [Python Numpy计算各类距离](https://blog.csdn.net/qq_19707521/article/details/78479532 )
2. [split()和array_split()](https://blog.csdn.net/autoliuweijie/article/details/51968315 )
3. [将数组区分成固定大小](https://www.geeksforgeeks.org/break-list-chunks-size-n-python/ )
```
def divide_chunks(l, n):
     
    # looping till length l
    for i in range(0, len(l), n): 
        yield l[i:i + n]
```