# Python Everyday 09: get n largest or smallest nums

How can we get the n largest items from a list, you may write code like this:

```
def nlargest_sort(a_list, n):
    if n > len(a_list):
        print("not enough nums")
    else:
        a_list.sort()
        return a_list[-n:][::-1]

a = [1, 45, 98, 980, 302, 23, 45, 66, 76, 34, 23, 45, 65, 4, 545, 65]
print(nlargest_sort(a, 3))
# Outputs: [980, 545, 302]
``` 

It's will work, but we can use 'heapq' to write much shorter and more efficient code：

```
def nlargest_heapq(a_list, n):
    if n > len(a_list):
        print("not enough nums")
    else:
        return heapq.nlargest(n, a_list)

a = [1, 45, 98, 980, 302, 23, 45, 66, 76, 34, 23, 45, 65, 4, 545, 65]
print(nlargest_heapq(a, 3))
# Outputs: [980, 545, 302]
```

Similarly to "n largest", you can use 'heap.nsmallest(n, some_list)' to get the n smallest nums from a list.