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

