## Recursive O(2<sup>n</sup>)
```python
def fibonacci(n):
    if n < 2:
        return n
    return fibonacci(n-1) + fibonacci(n-2)
```

## Iterative O(n):
```python
def fibonacci(n):
    fib_list = [0,1]
    if n < 0:
        return 'invalid n'
    i = 2
    while i < n +1:
        fib_list.append(fib_list[i-1] + fib_list[i-2])
        i += 1
    return fib_list[n]
```

## Memoized
```python
calculations = 0

def fibonacci():
    cache = {}
    def calculate_fib(n):
        global calculations
        calculations += 1
        if n in cache:
            return cache[n]
        else:
            if n < 2:
                return n
            cache[n] = calculate_fib(n-1) + calculate_fib(n-2)
            return cache[n]
    return calculate_fib


my_fib = fibonacci()
print(my_fib(15), calculations)
```