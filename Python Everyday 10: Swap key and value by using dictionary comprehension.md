# Python Everyday 10: Swap key and value by using dictionary comprehension

How to swap key and value for a dict in Python, like this?

```
count = {'first': 1, 'second': 2, 'third': 3}

for key in count:
    reverse_count[count[key]] = key

print(reverse_count)
# Output:
# {1: 'first', 2: 'second', 3: 'third'}
```

By using dictionary comprehension, we can do this in one line:

```
"""
Python Everyday 10 :Swap key and value
"""

count = {'first': 1, 'second': 2, 'third': 3}
reverse_count = {key: value for value, key in count.items()}

print(reverse_count)
# Output:
# {1: 'first', 2: 'second', 3: 'third'}
```