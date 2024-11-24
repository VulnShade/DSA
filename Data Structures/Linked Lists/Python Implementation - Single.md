```python
class Node:
    def __init__(self, data, next=None):
        self.data = str(data)
        self.next = next

    def __repr__(self):
        return self.data


class LinkedList:
    def __init__(self, data):
        node = Node(data)
        self.head = node
        self.tail = node
        self.length = 1

    def __repr__(self):
        node = self.head
        nodes = []
        while node is not None:
            nodes.append(node.data)
            node = node.next
        nodes.append("None")
        return f"""
            head: {self.head.data}, {self.head.next}
            tail: {self.tail.data}, {self.tail.next}
            length: {self.length}
            {" -> ".join(nodes)}
        """

    def append(self, data):
        new_node = Node(data)
        self.tail.next = new_node
        self.tail = new_node
        self.length += 1

    def prepend(self, data):
        new_node = Node(data, self.head)
        self.head = new_node
        self.length += 1

    def traverse_to_index(self, index):
        current_node = self.head
        i = 0
        while i < index-1:
            current_node = current_node.next
            i += 1
        return current_node

    def insert(self, index, data):
        if index == 0:
            self.prepend(data)
        if index == self.length or index > self.length:
            self.append(data)
        leader_node = self.traverse_to_index(index)
        new_node = Node(data, leader_node.next)
        leader_node.next = new_node
        self.length += 1

    def remove(self, index):
        if index == 0 or index < 0:
            self.head = self.head.next
            self.length -= 1
            return
        if index == self.length > self.length - 1:
            return
        leader = self.traverse_to_index(index)
        item_to_delete = leader.next
        leader.next = item_to_delete.next
        self.length -= 1
```