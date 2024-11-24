```python 
class Node:
    def __init__(self, data, next=None):
        self.data = str(data)
        self.next = next

    def __repr__(self):
        return self.data


class Queue:
    def __init__(self):
        self.first = None
        self.last = None
        self.length = 0

    def peek(self):
        return self.first.data

    def enqueue(self, value):
        new_node = Node(value)
        if not self.first:
            self.first = new_node
            self.last = new_node
            return
        self.last.next = new_node
        self.last = new_node
        self.length += 1

    def dequeue(self):
        if self.first:
            value = self.first.data
            self.first = self.first.next
            self.length -= 1
            return value
```