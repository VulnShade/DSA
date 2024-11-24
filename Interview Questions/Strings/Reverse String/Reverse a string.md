## With for loop:
```python
def reverse(string_to_reverse):
    """Reverse a given string."""
    if not string_to_reverse or \
        not isinstance(string_to_reverse, str) or \
            len(string_to_reverse) < 2:
        return 'Check input.'
    reversed_string = []
    for i in range(len(string_to_reverse)-1,-1,-1):
        reversed_string.append(string_to_reverse[i])
    return ''.join(reversed_string)
```

<br>

## With Python built-in methods:
```python
def reverse(string_to_reverse):
    """Reverse a given string."""
    if not string_to_reverse or \
        not isinstance(string_to_reverse, str) or \
            len(string_to_reverse) < 2:
        return 'Check input.'
    reversed_string = list(string_to_reverse)
    reversed_string.reverse()
    return ''.join(reversed_string)
```
