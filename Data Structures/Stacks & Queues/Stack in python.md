```python
class Node:
    def __init__(self, data, next=None):
        self.data = str(data)
        self.next = next

    def __repr__(self):
        return self.data


class Stack:
    def __init__(self):
        self.top = None
        self.bottom = None
        self.length = 0

    def peek(self):
        return self.top.data

    def push(self, value):
        new_node = Node(value)
        if not self.top:
            self.top = new_node
            self.bottom = new_node
            return
        new_node.next = self.top
        self.top = new_node
        self.length += 1

    def pop(self):
        if self.top:
            value = self.top.data
            self.top = self.top.next
            self.length -= 1
            return value
```