# Python Everyday 18: Combining two iterables with 'zip'

When you wanna combine two iterables, 'zip' function may be your best choose, the code sample as follow:

```

a = [1, 2, 3]
b = ['a', 'b', 'c']

z = zip(a, b)
for item in z:
    print(item)
    
# outputs:
'''
(1, 'a')
(2, 'b')
(3, 'c')
'''

```