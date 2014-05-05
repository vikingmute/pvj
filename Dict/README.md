###字典 哈希 map  object 不管你怎么叫他
用键值的方法储存数据 像一本字典 可以用部首索引他对应的文字 和List相比 
* 查找 插入速度非常快
* 但是内存占用很大 
* key是独一无二的

来一个dict
```python
heat = {'james':28, 'wade':30, 'bosh':29}
heat['james']
#28
heat.get('james')
#28
```
dict的长度
```python
len(heat)
```
增删改
```python
heat['ray'] = 34
#{'james':28, 'wade':30, 'bosh':29, 'ray':34}
heat.pop('ray')
#{'james':28, 'wade':30, 'bosh':29}
heat.clear()
#{}
#将另外一个dict添加进 heat中
heat.update({'james':28, 'wade':30, 'bosh':29})
#{'james':28, 'wade':30, 'bosh':29}
heat.update({'james':24, 'ray':34})
#{'james':24, 'wade':30, 'bosh':29, 'ray':34}
#哈哈 很像js的extend方法
```

上面的用js写一遍

```js
var heat = {'james':28, 'wade':30, 'bosh':29};

heat['james']
heat.james
//james

//获取object长度 用es5的方法
Object.keys(heat).length
```
