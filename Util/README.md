###常用内置模块
Python有很多非常还用的内置模块 当然还有很多别人写好的很叼的第三方库 这里我们介绍一些好用的内置模块
####Urllib2
抓取网页并且分析 是我们经常做的事情了 用这个模块可以完成这一系列的操作
```python
#一个很简单的抓取列子
import urllib2
response = urllib2.urlopen('http://www.baidu.com')
html = response.read()
#也可以传入一个Request对象
req = urllib2.Request('http://www.baidu.com')
response = urllib2.urlopen(req)
html = response.read()

#复杂一些 我们添加一些data和headers
import urllib

url = "http://viking.com/commit-info"
userAgent = "Mozilla/4.0 (compatible; MSIE 5.5; Windows NT)"
values = {
	'name': 'viking',
	'sex': 'male'
}
headers = {
	'User-Agent': userAgent
}
data = urllib.urlencode(values)
req = urllib2.Request(url, data, headers)
response = urllib2.urlopen(req)
html = response.read()

```

在nodejs中 我们也可以用Request对象来实现相同的方法 请注意异步变成的不同哈
```javascript
var request = require('request');
var querystring = require('querystring')
var url = "http://viking.com/commit-info";
var userAgent = "Mozilla/4.0 (compatible; MSIE 5.5; Windows NT)";
var values = {
	'name':'viking',
	'sex': 'male'
};
var headers = {
	'User-Agent':userAgent
};
var data = querystring.stringify(values);
var options = {
	uri: url,
	qs: data,
	headers: headers,
	method: 'POST'
};

request(options, function(error, response, body) {
	console.log(body);
});


```


