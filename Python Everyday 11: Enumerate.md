# Python Everyday 11: Enumerate

Today I write a sample to show how to use "enumerate", it's simple but very useful:

```
"""
Python Everyday 11: enumerate
"""

pet = ["cat", "dog", "bird", "fish", "rabbit"]
for counter, value in enumerate(pet, 1):
    print(c, value)

#Outputs:
# 1 cat
# 2 dog
# 3 bird
# 4 fish
# 5 rabbit
```