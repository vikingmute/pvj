###字符串
不逼逼了 直接上代码 喜欢python的字符串切片功能啊


来一个字符串
```python
viking = 'tattoo on my shoulder'
#各种切片玩
viking[0]
#'t'
viking[0:6]
#'tattoo'
viking[-8:]
#可以省略偶 很好用 'shoulder'
```

当你要格式化一个字符串的时候 可以这么搞一下 
```python
'Hey, name is %s, score is %d' % ('viking', 60)
# hey, name is viking, score is 60
'your height is %.2f' % 160.22223456
# your height is 160.22

#常用的就有 %d(digital), %f(float), %s(string)
```
关于字符串 你必须读的一个链接 
[廖雪峰的python教程](http://www.liaoxuefeng.com/wiki/001374738125095c955c1e6d8bb493182103fac9270762a000/001386819196283586a37629844456ca7e5a7faa9b94ee8000)

上面的用js写一遍

```javascript
var viking = 'tattoo on my shoulder';
//切片就比较蛋疼了
viking.substring(0, 1);
viking.substring(0, 6);
//还有一个方法substr 第二个参数是要切字母的个数
viking.substr(1, 3);
	
//没有负数索引

//格式化字符串没有原生的方法 但是我们可以在node中找到类似的方法format
var util = require('util');
util.format('name is %s, score is %d', 'viking', 60);

//没有float类型但是 多了一个json类型
util.format('%j', {name: 'viking'});
//直接输出{name: 'viking'}

```

