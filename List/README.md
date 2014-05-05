###在python中被叫做List，在js中被叫做Array 一个玩意儿

新建一个数组
```python
players = ['James', 'Wade', 'Bosh']
```

数组长度
```python
len(players)
#输出3
```

访问数组元素 可以使用负数
```python
print players[1]
#输出 wade
print players[-1]
#输出 Bosh
```
增删改
```python
#末尾增加一个
players.append('Ray Allen')
#['James', 'Wade', 'Bosh', 'Ray Allen']

#指定位置增加一个
players.insert(1, 'Jones')
#['James', 'Jonens', Wade', 'Bosh', 'Ray Allen']



#删除一个元素
players.pop()
#['James', 'Jonens', Wade', 'Bosh']
players.pop(2)
#['James', 'Jonens', 'Bosh']

#修改一个元素
players[2] = 'Chris Bosh'
#['James', 'Jonens', 'Chris Bosh']

#末尾增加另外一个列表
players.extend(['Wade', 'Cole'])
#['James', 'Jonens', 'Chris Bosh', 'Wade', 'Cole']

```

判断一个元素是不是List对象
```python
isinstance(players, list)
#输出True
```

用js把上面的方法都写一遍...有的地方确实蛋疼啊
```js
var players = ['James', 'Wade', 'Bosh'];
console.log(players.length);
console.log(players[1]);
//不支持负数index

players.push('Ray Allen');
//['James', 'Wade', 'Bosh', 'Ray Allen'];

players.splice(1, 0, "Jones");
//['James', 'Jonens', Wade', 'Bosh', 'Ray Allen'];
//神奇的方法啊，牛逼的splice，当然这是反话

players.pop();
//['James', 'Jonens', Wade', 'Bosh']

players.splice(2, 1);
//['James', 'Jonens', 'Bosh']
//splice又来了，真是厉害..

players[2] = 'Chris Bosh';
//['James', 'Jonens', 'Chris Bosh']

players = players.concat(['Wade', 'Cole']);
//['James', 'Jonens', 'Chris Bosh', 'Wade', 'Cole']

//前方高能 判断一个变量是不是数组 要用这么多奇葩的方法 呵呵
players instanceof Array;
//True

//tricky的傻逼方法
Object.prototype.toString.call(players) == '[object Array]';
//true

//es5标准方法 当然还要浏览器大神的支持
Array.isArray(players);
//true
```

好吧 我爱python 下节讲讲数组的循环

