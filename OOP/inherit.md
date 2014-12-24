###类的继承

当我们定义一个class的时候，可以从某个现有的class继承，新的class称为子类（Subclass），而被继承的class称为基类、父类或超类（Base class、Super class）。

直接用代码来看

```python
def Animal(object):
	def run(self):
		print 'animal is running'

def Cat(Animal):
	pass

def Dog(Animal):
	pass

kitty = Cat()
kitty.run()
# 'animal is running'
doggy = Dog()
doggy.run()
# 'animal is running'
```

###多态

说的很玄乎 其实就是子类覆盖父类的方法

```python
def Animal(object):
	def run(self):
		print 'animal is running'

def Dog(Animal):
	def run(self):
		print 'dog is running'
doggy = Dog()
doggy.run()
#' dog is running'
```

