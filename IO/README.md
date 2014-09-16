###介绍一下python的IO操作

我们从最简单的文件读取和写入说起

```python
#open a file 
f = open('test.txt', 'r')

f.read()
#output "this ain't cool"

f.close()

# you can use with, more easier

with open('test.txt', 'r') as f
    f.read()

#write to a file, if not exsits, create it
# mode a to append content to the end
with open('test.txt', 'w+') as f
    f.write('stop crying...')

# if the file is very long, you can read by lines
for line in f.readlines():
    print line

```

我们再来看看nodejs是怎么来读写文件的
```javascript
var fs = require('fs')

fs.readFile('test.txt', 'utf8', function(err, data){
    if (err) {
        console.log(err);
    } else {
        console.log(data);
    }
});

fs.writeFile('new.txt', 'bitch better have my money', function(err, data){
    if (err) {
        throw err;
    } else {
        console.log('write sth into new.txt');
    }
});
```
