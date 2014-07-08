### 数组的迭代

python迭代是一件很开心的事情 只要是可迭代对象都可以开心的迭代 字符串 数组 字典 都可以迭代
使用for in 来完成迭代 比js或者c++这种使用下标迭代的抽象程度要高， 好了 开始看代码

```python
players = ['james', 'gurin', 'teo']
for name in players:
    print name
# ouput: 'james, gurin, teo'

#需要下标怎么办?
# solution 1
for index in range(0, len(players)):
    print str(index) + " : " + players[index]

# solution 2 enumerate
for index, name in enumerate(players):
    print str(index) + " : " + name
```
