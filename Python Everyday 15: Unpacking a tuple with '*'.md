# Python Everyday 15: Unpacking a tuple with '*'

Today I will show a little trick, it's a shortcut for unpacking a tuple, just with '*' ,  here it is:

```
users = [
('Jerry', 182, 170),
('Mark', 152, 144),
('Frank', 172, 162),
]

for u in users:
    print('Name={}, Height={}, Weight={}'.format(*u))

'''
Outputs:
Name=Jerry, Height=182, Weight=170
Name=Mark, Height=152, Weight=144
Name=Frank, Height=172, Weight=162
'''
```