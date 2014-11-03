####现在我们来感受一下 python对系统和文件的一些操作 

本来内容应该会非常多的 我们这里就稍微简化一下 长话短说

```python
import os
print os.name
#output 'posix'
os.getenv('PATH')
#'/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/bin:/opt/X11/bin:/usr/local/mysql/bin'
os.path.join('/Users/michael', 'testdir')
os.mkdir('/Users/michael/testdir')
os.rmdir('/Users/michael/testdir')
os.rename('test.txt', 'test.py')
os.remove('test.py')
#check a file or a folder exsits
os.path.exsits(fname)
#return True or false
os.path.split('/Users/michael/testdir/file.txt')
#return path and filename with extention as a tuple ('/Users/michael/testdir', 'file.txt')
os.path.splittext('/path/to/file.txt')
#return file and extention as a tuple ('/path/to/file', '.txt')

#use third-party module to do some copy works
import shutil
shutil.copyfile('test.py', 'test2.py')

#get current path
os.getcwd()
#cd a dir 
os.chdir('./jsfiles')
#go through all the files in this level
os.listdir('.')
#['a.js', 'b.js', 'c.js', 'test.txt']
# check files with .js extention
# method one
for file in os.listdir('.'):
    if file.endswith('.js')
        print file
[x for x in os.listdir('.') if x.endswith('.js')]
# return ['a.js', 'b.js', 'c.js']

#method two, using glob
import glob
glob.glob('*.js')
['a.js', 'b.js', 'c.js']

#method three, using os.walk() deeper to all the subfolders
for root, dirs, files in os.walk('.'):
    for f in files:
        if f.endswith('.js'):
            print os.path.join(root, f)


```
