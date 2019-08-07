# Python Everyday 21: Taking some actions before leaving by using atexit

By using the -i option, we can execute *.py script before entering the interpreter, moreover, with the "atexit", we also can taking some actions before leaving, here is a sample:


```
import atexit

@atexit.register
def Bye():
    print("Leaving ...")
    print("Bye, bye, butterfly ~")

'''
$ python3 -i pe21.py
>>> exit()
Leaving ...
Bye, bye, butterfly ~
'''
```