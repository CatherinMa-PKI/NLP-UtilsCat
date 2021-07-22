## 月经史
#### 初潮年龄
```Python
def doCall(text):
  pattern1 = '(\d+)\w?\S\d+(?=月经)|(?<=初潮)(\d+)|(?<=初潮 )(\d+)|(?<=初潮：)(\d+)|(\d+)\S(?=初潮)|((?<=月经史：)|(?<=月经：)|(?<=月经))(\d+)\w?\S\d+|(?<=月经)(\d+)(?=岁)' 
  result1=re.findall(pattern1,text)
    if len(result1)>0:
      i=0
      while len(result1[0][i])==0:
        i+=1
      cc=result1[0][i]
  return cc
```
#### 生育子女个数
```Python
def doCall(text):
  pattern2 ='((?<=妊娠)|(?<=生育)|(?<=育有)|(?<=产))(\d+)|((?<=妊娠)|(?<=生育)|(?<=育有)|(?<=产)) (\d+)|((?<=妊娠)|(?<=生育)|(?<=育有)|(?<=产))(\S)次'
  result2=re.findall(pattern2,text)
    if len(result2)>0:
      i=0
      while len(result2[0][i])==0:
        i+=1
      syzngs=result2[0][i]
  return syzngs

```
