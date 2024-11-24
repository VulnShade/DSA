## Using closure to provide caching

```python
def memoize_add_to_80():
    cache = {}

    def calc(n):
        if n in cache:
            return cache[n]
        print('Long time.')
        cache[n] = n + 80
        return cache[n]

    return calc  # Return the function itself, not a call to it


memoize = memoize_add_to_80()
print(memoize(5))
print(memoize(6))
print(memoize(5))
```