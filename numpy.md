1. [numpy中的范数计算方法 linalg.norm](https://zhuanlan.zhihu.com/p/33217726 )
2. [np.linalg.norm(求范数) - QingHaoHuang - CSDN博客](https://blog.csdn.net/hqh131360239/article/details/79061535 )
2. [Python Numpy计算各类距离](https://blog.csdn.net/qq_19707521/article/details/78479532 )
2. [split()和array_split()](https://blog.csdn.net/autoliuweijie/article/details/51968315 )
3. [将数组区分成固定大小](https://www.geeksforgeeks.org/break-list-chunks-size-n-python/ )
4. [Structured arrays — NumPy v1.15 Manual](https://docs.scipy.org/doc/numpy-1.15.0/user/basics.rec.html )
```
def divide_chunks(l, n):
     
    # looping till length l
    for i in range(0, len(l), n): 
        yield l[i:i + n]
```