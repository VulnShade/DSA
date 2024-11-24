## Binary Tree
- Each node can have 0, 1, or 2 child nodes
- Each child can only have 1 parent


<br>
<div align='center'>

| Operation    | Time Complexity | Example (Python)           |
| ------------ | --------------- | -------------------------- |
|lookup        | O(log n)        | 		         |
|insert   	    | O(log n)        |				   |
|delete        | O(log n)        | 	 	 |


</div>

<br>

### Terminology:
- **Perfect Binary Tree**
	- all nodes have 0 or 2 children
	- bottom layer completely filled
- **Full Binary Tree**
	- all nodes have either 0 or 2 children
	- never 1 child
<br>

### Perfect Binary Tree
- \# nodes in level = 2<sup># of level</sup> (levels start at 0)
- \# total nodes = 2<sup>height</sup> - 1
- log nodes = height

<br>


<div align='center'><img src="../../_resources/636f9d5d51298b89476aa5440b9edea9.png" width=75%><div