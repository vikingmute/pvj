### Python的json转换工具
我们这里只说非常简单的功能 在dict对象和json string之间来回转换

```python
import json
a = {'name': 'viking', 'age': 26}
b = json.dumps(a)
# ouput: '{"age": "20", "name": "viking"}'
c = json.loads(b)
# return a dict type: {u'age': u'20', u'name': u'viking'}
```

javascript也提供了相同的功能 不过要注意兼容性问题 旧版浏览器可以引入json2.js文件

```javascript
var a = {'name': 'viking', 'age': 26};
JSON.stringify(a);
// return a string type
var b = '{"name": "viking"}';
JSON.parse(b);
// return a javascript object type
```
