# Python Everyday 08: Record func execution time in a Pythonic way


I've been asked many times how to print the function execution time. In my opinion, it's better to use decorators than write the count code for func every time. More importantly, this is Pythonic.  Let's see how to do this:

```
"""
Python Everyday 08:  record execution time in Pythonic way
"""
from functools import wraps
import datetime as dt


def TimeCounter(func):
    @wraps(func)
    def counter(*args, **kwargs):
        start_time = dt.datetime.now()
        func(*args, **kwargs)
        end_time = dt.datetime.now()
        spend_time = (end_time - start_time).total_seconds()
        print(func.__name__ + " cost: ", spend_time, "s")
    return counter


@TimeCounter
def addition_func(x):
    while x < 1000000:
        x = x + 1
    print("This is boring")


addition_func(1)
```

Outputs:
```
This is boring
addition_func cost:  0.0231132 s
```