###在python中使用模块

在python中使用模块是一件非常简单的事情 我们自己创建一个模块 然后再引入他

```python
# -*- coding: utf-8 -*-
'a test module you can use'
__author__ = 'vikingmute'

#we can import other modules here

import sys

def test():
    args = sys.argv
    if len(args) == 1:
        print "Hello Man~"
    elif len(args) == 2:
        print "Hello" + str(args[1])
    else:
        print "too many arguments"
#if load it from the console, run it now
if __name__ == 'main':
    test()
    
```

模块这样就创建好了 保存这个文件 叫做hello.py  可以直接在bash下使用 这样会直接调用该函数（看代码最后两行）

```bash
$ python hello
Hello man~
$ python hello viking
Hello viking
```

```bash
$ python
Python 2.7.5 (default, Aug 25 2013, 00:04:04) 
[GCC 4.2.1 Compatible Apple LLVM 5.0 (clang-500.0.68)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> import hello
>>> hello.test()
>>> 'Hello man~'
```

Javascript的模块化道路经过了漫长的发展 我们先说说在nodejs中标准的commonJs规范
这里是官方网站可以看看 http://wiki.commonjs.org/wiki/CommonJS
commonJS一般是在服务器端使用 其实写法和其他的语言也差不多了 不同的就是有一个exports模块来输出
```javascript
/*
 * @file a simple javascript module
 * @author vikingmute
*/ 

exports.trim = function (str) {
    return str.replace(/^\s*|\s*$/g, '');

} 
```

在另外一个foo.js中
```javascript
var tool = require('./tools');
var shitty = "   my name is asshole    ";
console.log(tool.trim(shitty));
// output "my name is asshole";
```
