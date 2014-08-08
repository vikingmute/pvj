### 来说一说时间这个对象

```python
#output all current dates
from datetime import datetime
import time
today = datetime.date.now()
print today.hour
print today.minute
print today.year
print today.month
print today.day
print today.second
#output current dates in timestamp
#有点烦人 太难记了
timestamp = time.mktime(today.timetuple)
#convert back
today = datetime.date.fromtimestamp(timestamp)

# easy way
print time.strftime('%d/%m/%Y %H:%M:%S')

```

太烦了 找了半天 我们看看js的吧...
当然你可以用moment这个库...
```javascript
var today = new Date();
today.getFullYear();
//之类之类这里不写了
var timestamp = new Date().getTime();
//注意这里是乘了1000的
var today_2 = new Date(timestamp);
moment.format('dd/MM/YYYY HH:mm:ss');
```
