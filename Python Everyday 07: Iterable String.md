# Python Everyday 07: Iterable String

How can make string in Python to be iterable, I can show you a way by using 'iter()', a sample exp as follow:

```
"""
Python Everyday 07: Iterable String
"""
string = "0123456789"
str_iter = iter(string)
for i in range(len(string)):
    print(next(str_iter))
```

Outputs:

```
0
1
2
3
4
5
6
7
8
9
```