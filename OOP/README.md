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

js没有类的概念 所以的都是用object来实现的 我们这里可以用原型链来实现一个class的概念
```js
function Person(name) {
    //构造函数
    this.name = name;
    //没有私有变量这个概念 我们这里只是这样模拟下
    this._privateName = 'sneaky little jew';
}
var fn = Person.prototype;
fn.speak = function () {
    console.log('i am ' + this.name);
}

var viking = new Person('viking');
viking.speak();
// 'i am viking'

//检测一下实例和构造函数
console.log(viking instanceof Person);
console.log(Person.prototype.contructor === Person);
// true , true
//new做了什么？
//在构造函数里面  首先创建一个空的 {} 将this里面的属性都添加进去
//将这个对象的__proto__对象链接到prototype上
//返回这个对象

```
