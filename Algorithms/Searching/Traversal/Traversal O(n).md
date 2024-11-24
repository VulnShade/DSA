## BFS
- Best if node is towards top
<div style="display: flex;">
<div style="flex: 1; padding-right: 10px;">

### Pros:
- Finding Shortest Path
- Closer Nodes
	</div>
<div style="flex: 1;">

### Cons:
- More Memory
	</div></div>
<br>
	
	
## DFS
<div style="display: flex;">
<div style="flex: 1; padding-right: 10px;">

### Pros:
- Less Memory
- Does path exist? (from source to target node)
	</div>
<div style="flex: 1;">

### Cons:
- Can get slow
	</div></div>
<br>
	
## Questions:
If you know a solution is not far from the root of the tree:
BFS

If the tree is very deep and solutions are rare: 
BFS - DFS will be slower

If the tree is very wide:
DFS - BFS will need too much memory, in a queue

If solutions are frequent but located deep in the tree:
DFS

Determining whether a path exists between two nodes:
DFS

Finding the shortest path:
BFS