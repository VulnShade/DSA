```python
class Node:
    # Constructor to create a new node
    def __init__(self, key):
        self.key = key
        self.left = None
        self.right = None
 
# A utility function to insert
# a new node with the given key in BST
def insert(node, key):
    # If the tree is empty, return a new node
    if node is None:
        return Node(key)
 
    # Otherwise, recur down the tree
    if key < node.key:
        node.left = insert(node.left, key)
    elif key > node.key:
        node.right = insert(node.right, key)
 
    # Return the (unchanged) node pointer
    return node

root = insert(root, 9)
insert(root, 4)
insert(root, 6)
insert(root, 20)
insert(root, 170)
insert(root, 15)
insert(root, 1)
```