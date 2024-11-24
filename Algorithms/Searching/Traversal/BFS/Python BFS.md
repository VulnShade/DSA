```python
def bfs(node):
    if not node:
        return None
    list = []
    queue = []
    queue.append(node)
    while queue:
        current_node = queue.pop(0)
        list.append(current_node.key)
        if current_node.left:
            queue.append(current_node.left)
        if current_node.right:
            queue.append(current_node.right)
    return list
```
<br>

### Recursive
```python 
def bfs_recursive(queue, list):
    if not queue:
        return list
    current_node = queue.pop(0)
    list.append(current_node.key)
    if current_node.left:
        queue.append(current_node.left)
    if current_node.right:
        queue.append(current_node.right)
    return bfs(queue, list)
