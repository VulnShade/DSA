```python
def dfs_inorder(root):
    return traverse_in_order(root, [])

def traverse_in_order(node, list):
    if node.left:
        traverse_in_order(node.left, list)
    list.append(node.key)
    if node.right:
        traverse_in_order(node.right, list)
    return list
```

```python
def dfs_preorder(root):
    return traverse_preorder(root, [])

def traverse_preorder(node, list):
    list.append(node.key)
    if node.left:
        traverse_preorder(node.left, list)
    if node.right:
        traverse_preorder(node.right, list)
    return list
```

```python
def dfs_post_order(root):
    return traverse_post_order(root, [])

def traverse_post_order(node, list):
    if node.left:
        traverse_post_order(node.left, list)
    if node.right:
        traverse_post_order(node.right, list)
    list.append(node.key)
    return list
```