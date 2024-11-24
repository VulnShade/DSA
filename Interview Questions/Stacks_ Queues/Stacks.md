## Checking correct order

### Opening brackets match closing
O(n) time and space
```python
def isValid(self, s: str) -> bool:
	stack = []
	matching = {"(": ")", "[": "]", "{": "}"}

	for c in s:
		if c in matching: # if c is an opening bracket
			stack.append(c)
		else:
			if not stack:
				return False

			previous_opening = stack.pop()
			if matching[previous_opening] != c:
				return False

	return not stack
```


### Removing adjacent duplicate letters:
O(n) time and space
```python
def removeDuplicates(self, s: str) -> str:
	stack = []
	for c in s:
		if stack and stack[-1] == c:
			stack.pop()
		else:
			stack.append(c)

	return "".join(stack)
```


### String match after backspace (#)
O(n) time and space
```python
def backspaceCompare(self, s: str, t: str) -> bool:
	def build(s):
		stack = []
		for c in s:
			if c != "#":
				stack.append(c)
			elif stack:
				stack.pop()

		return "".join(stack)

	return build(s) == build(t)
```