# Python Everyday 17: Make friend with 'yield'

Make friend with 'yield', it will help you save tons of cache storages. Let's see how to use 'yield' to generate a Fibonacci sequence, the code as follow:

```
def fib():
    a, b = 0, 1
    while True:
        yield a
        a, b = a + b, a


for i in fib():
    print(i)
    if i > 1000:
        break
```

Note that in Python 3.*, you also can use 'fib().__next__()' to run generate iteration. Tomorrow, I will drive all day, the update may be delayed, I hope not.