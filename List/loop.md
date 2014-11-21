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

javascript循环数组的方法 经典的方法

```javascript
var players = ['james', 'gurin', 'teo'];

for (var i = 0; i < players.length; i++) {
    console.log(i + ':' + players[i]);    
}

//我们一直都说不要用for in来循环数组 为啥呢
//请看下面的链接 http://stackoverflow.com/questions/500504/why-is-using-for-in-with-array-iteration-such-a-bad-idea
//最主要的原因是原型链被污染的时候 上面的东西都会被搞出来 还有就是顺序会出问题

//es6里面可以用for of方法来直接循环出数组的值 而不是索引 类似python

for (var player of players) {
    console.log(player);
}
```
