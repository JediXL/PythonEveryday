# Python Everyday #01 Local VS Global

I saw a good question from Ins：

```
def foo(k):
    k = [1]

q = [0]
foo(q)
print(q)

"""
Ans is:
A : [0]
B : [1]
C : [0,1]
D : [1,0]
"""
```

---------
The right answer is A, due to local k is local and foo() without return.