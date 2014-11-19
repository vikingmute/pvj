## 正则是个很大的话题 

这里就放在字符串的模块里面 简单的python使用这则的方法

### 简单的规则
* . (a period) -- matches any single character except newline '\n'
* \w -- (lowercase w) matches a "word" character: a letter or digit or underbar [a-zA-Z0-9_]. Note that although "word" is the mnemonic for this, it only matches a single word char, not a whole word. \W (upper case W) matches any non-word character.
* \s -- (lowercase s) matches a single whitespace character -- space, newline, return, tab, form [ \n\r\t\f]. \S (upper case S) matches any non-whitespace character.
* \t, \n, \r -- tab, newline, return
* \d -- decimal digit [0-9] (some older regex utilities do not support but \d, but they all support \w and \s)
* ^ = start, $ = end -- match the start or end of the string
* \ -- inhibit the "specialness" of a character. So, for example, use \. to match a period or \\ to match a slash.

```python
import re
text = "viking"
result = re.search(r'vik', text)
print result.group()
# "vik"
text = "vik123vi"
result = re.search(r'\d\d\d', text)
text = "@@@%%vi1"
result2 = re.search(r'\w\w\w', text)
# "vi1"
```

### 重复
* + -- 1 or more occurrences of the pattern to its left, e.g. 
* * -- 0 or more occurrences of the pattern to its left
* ? -- match 0 or 1 occurrences of the pattern to its left

```python
text = "piiiiigt"
result = re.search(r'pi+', text)
# "piiiii"
```

### 方括号

Square brackets can be used to indicate a set of chars, so [abc] matches 'a' or 'b' or 'c'. 
```python
text = "abcdefg"
result = re.search(r'[abc]+', text)
# "abc"
```

###分组
The "group" feature of a regular expression allows you to pick out parts of the matching text.  To do this, add parenthesis ( )

```python
text = "alice.matter@google-inc.com"
result = re.search(r'([\w.]+)@([\w.-]+)', text)
result.group()
# "alice.matter@google-inc.com"
result.group(1)
# "alice.matter"
result.group(2)
# "google-inc.com"

```
###Findall

findall() is probably the single most powerful function in the re module. Above we used re.search() to find the first match for a pattern. findall() finds *all* the matches and returns them as a list of strings, with each string representing one match.

```python
text = "me@we.com some crap bitch@nword.com"
result = re.findall(r'\w+@[\w.]+', text)
print result
# ["me@we.com", "bitch@nword.com"]
```

### 贪婪和非贪婪
现在有一段html文本 "<a>some nice dudes</a> test some data haha" 我想匹配这里面你的html tag，我们来写一个正则 <.*> 但是你会发现匹配到了"<a>some nice dudes</a>" 怎么样让正则遇到一个符合条件的停下 不继续往下面匹配呢？ 很简单 不让正则贪婪 只要前面加一个问号就好了 写成这样 <.*?> 
```python
text = "<a>some nice dudes</a>"
result = re.findall(r'<.*?>')
print result
# ['<a>', '</a>']
```

### 替换
直接看代码吧
```python
text = "<a> some nice dudes</a>"
result = re.sub('<.*?>', '', text)
print result
# "some nice dudes"
```

##javascript版本代码
javascript 有比较多的正则方法 
Regex对象下有 exec 和 test 方法
String对象下有 match search 和 replace
如果你先检验一个字符串符合不符合一个正则 可以用test和search方法
如果你想返回一些符合特点样式的结果 你可以使用 exec 和match方法 注意exec只能返回一个结果 而match可以返回多个
如果是多个group结果 要使用exec方法
如果你想替换 使用replace方法
```javascript
var a = 'viking';
var pa = /vik/g;
pa.test(a);
//true
a.search(pa)
//0 如果找不到返回-1
a = "me@gmail.com abcd you@me.com";
pa = /\w+@[\w.]+/g;
a.match(pa);
// ['me@gmail.com', 'you@me.com']
pa.exec(a);
// ['me@gmail.com'] 只返回第一个
pa = /(\w+)@([\w.]+)/;
pa.exec(a);
// ['me@gmail.com', 'me', 'gmail.com']

//如果想要分组加findall的情况怎么办？

```
