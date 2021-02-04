# NLP-UtilsCat
医院NLP中涉及到的function，集合在这个包里面。

医院NLP中用到的一些function
===========================
#### import一些必要包
```
import time
import re
import numpy as np
import re
import copy
from pyltp import Segmentor ##导入ltp库
import functools
```
#### 读取文件
```
def UsualOpen(filename,encoding,colnames):
    with open(filename,encoding=encoding,errors='ignore') as f:
        contents = [line.rstrip("\r\n") for line in f]
    if colnames==True:
        colnames = contents[0].split("\t")
        contents = contents[1:]
        return contents,colnames
    else:
        return contents
```
#### 检查每一行的长度
```
def RowLengthCheck(contents,colnames): 
    i = 0
    index_list = []
    for idx,line in enumerate(contents):
        if len(line.split("\t"))!=len(colnames):
            i+=1
            index_list.append(idx)
    print(str(i)+" lines not satisfied")
    if i!=0:
        return index_list
```
