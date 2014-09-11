### Python 字典类型的循环 

强大的for功能 我们用下面的代码循环一个字典

```python

viking = {'name': 'viking', 'age': 28, 'sex': 'male'}

#基本的搞一下 很像js

for key in viking:
    print key
    print viking[key]

#可以直接获得dict的key的数组和值的数组

print viking.keys()
print viking.values()

#output ['name', 'age', 'sex'] ['viking', 28, 'male']

#还可以直接循环获取key和value
for k, v in viking.items():
    print k + ':' + str(v)

```
怎样 很方便吧~

我们来看看js怎么循环一个Object

```javascript
var viking = {'name': 'viking', 'age': 28, 'sex': 'male'};

for (var key in viking) {
    //notice, check the prototype
    if (viking.hasOwnProperty(key)) {
        console.log(key + ':' + viking[key]);
    }
}

//access keys array using es5

console.log(Object.keys(viking));


```
