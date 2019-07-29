# Python Everyday 12: how can u miss the defaultdict ?

When you wanna use a dict for item counting, you will get the KeyError as follow:

```
pets = ["duck", "duck", "bird", "cat", "dog", "dog", "fish"]
petCounter = dict()

for p in pets:
    petCounter[p] += 1
    
# >>> KeyError: 'duck'
```
Hence what we looking for is a dict, which can instantiate an obj when a key doesn't exist. "defaultdict" is the right answer.

```
"""
Ptyhon Everyday 12: defaultdict
"""

from collections import defaultdict
petCounter = defaultdict(lambda: 0)

for p in pets:
    petCounter[p] += 1

print(petCounter)

# defaultdict(<function <lambda> at 0x104e0b268>, {'duck': 2, 'bird': 1, 'cat': 1, 'dog': 2, 'fish': 1})

``` 