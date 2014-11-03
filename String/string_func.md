### 一些字符串的常用方法 
不多说了 直接干起代码来
```python
a = "Viking"
a.upper() 
# "VIKING"
a.lower()
# "viking"
a.find('ng')
# 4
a.find('sdgt')
# -1
a.replace('Viking', 'Weson')
# 'Weson' not supports exgex
b ="    James   ";
b.strip()
# 'James'
c = "kk jj tt"
d = c.split(' ')
# ['kk', 'jj', 'tt']
' '.join(d)
# 'kk jj tt'
```

用js来写一写哈
```javascript
var a = "Viking";
a.toUpperCase();
a.toLowerCase();
a.indexOf('ng');
a.indexOf('sdgt');
a.replace('Viking', 'Weson');
var b = "  James  ";
b.trim();
//for bowser doesn't support trim

if (!String.prototype.trim) {
    (function(){
        // Make sure we trim BOM and NBSP
        var rtrim = /^[\s\uFEFF\xA0]+|[\s\uFEFF\xA0]+$/g;
        String.prototype.trim = function () {
            return this.replace(rtrim, "");
        }
    })();
}

var c = "aa bb cc";
var d = c.split(' ');
d.join(' ');
```

