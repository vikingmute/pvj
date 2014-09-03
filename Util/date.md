### 来说一说时间这个对象

```python
import datetime
import time
#using datetime module
today = datetime.datetime.now()
print today.hour
print today.minute
print today.year
print today.month
print today.day
print today.second
#output current dates in timestamp
#有点烦人 太难记了
timestamp = int(time.time())
#convert back
today_two = datetime.date.fromtimestamp(timestamp)
print today_two.year

# using time strftime
print time.strftime('%d/%m/%Y %H:%M:%S')

#checking all the parameters and details here: 
# http://www.cyberciti.biz/faq/howto-get-current-date-time-in-python/

```



太烦了 找了半天 我们看看js的吧...
当然你可以用moment这个库...
```javascript
var today = new Date();
today.getFullYear();
//之类之类这里不写了
var timestamp = Math.round(new Date().getTime()/1000);
//注意这里是乘了1000的
var today_2 = new Date(timestamp * 1000);
today2.getFullYear();
moment.format('dd/MM/YYYY HH:mm:ss');
```
