###Python连接sqllite数据库

SQLite是一种嵌入式数据库，它的数据库就是一个文件。由于SQLite本身是C写的，而且体积很小，所以，经常被集成到各种应用程序中，甚至在iOS和Android的App中都可以集成。

Python就内置了SQLite3，所以，在Python中使用SQLite，不需要安装任何东西，直接使用。

下面直接上代码了

```python
import sqlite3
conn = sqllite3.connect('test.db')
c = conn.cursor()
#create a table
c.execute('create table user (id varchar(20) primary key, name varchar(20))')
#insert a record
c.execute('insert into user (id, name) values (\'1\', \'Michael\')')
#我们可以已参数的形式传入值 注意第二个参数是tuple类型
c.execute('insert into user (id, name) values (?, ?)', (2, 'James'))
#还可以一次插入多个值
data = [(3, 'Teo'), (4, 'Yepes'), (5, 'Zapata')]
c.executemany('insert into user (id, name) values (?, ?)', data)

#affect row
c.rowcount
#close cursor and conn
c.close()
conn.close()
```

你觉得一直要关闭连接太麻烦了 我们可以直接用with命令 看起来也方便很多 回调函数的快感

```python 
with sqlite3.connect(db_filename) as conn:
    with open(schema_filename, 'rt') as f:
        schema = f.read()
    #execute a script file
    conn.executescript(schema)
```

我们插入了数据 然后讲一下获取数据

```python
with sqlite3.connect(db_filename) as conn:
    c = conn.cursor()
    c.execute('select * from user');
    values = c.fetchall()
    value = c.fetchone()
    values2 = c.fetchmany(5)
    #可以获得不同长度的记录


```
