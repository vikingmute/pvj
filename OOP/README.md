###面向对象编程
给你一个类看看偶 这节只讲简单的类和实例

```python
class Person():
    """a class represent a person
    """
    def __init__(self, name='zhang', score=60):
        self.name = name;
        self.score = score;
        self.__sex = 'male'
        
    def show_score(self):
        print '%s: %d' % (self.name, self.score)
        
    def get_sex(self):
        return self.__sex
    def set_sex(self, sex):
        if sex == 'male' or sex == 'female':
            self.__sex = sex
        else :
            raise ValueError('bad sex')

viking = Person()

viking.show_score()

print viking.name

print viking.__sex

viking.set_sex('female')

print viking.get_sex()

weson = Person('cheng', 100)

weson.show_score()

"""
一个简单的类 两个实例 支持默认参数 没什么好说的
__sex参数说明私有变量 不能直接访问 要用getter 和 setter来设置他的值
"""


```


上面的用js写一遍

```js

```
