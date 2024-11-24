## Queues
- FIFO
 - Can be implemented via:
	- Arrays
	- Linked Lists
<br>
<div align='center'>

| Operation    | Time Complexity | Example (Python)           | Example (Javascript) | 
| ------------ | --------------- | -------------------------- | --------------------- |
|lookup        | O(n)            | `value in q`				         | `arr.indexOf(value);` |
|enqueue  	    | O(1)            |  `q.append()`						   |  `arr.unshift(value);` |
|dequeue       | O(1)            | `q.popleft())`					 	 |   `arr.pop();`      |
|peek         	| O(1)							|  `q[0]`  				        	  |   `arr[0]`          |

</div>
<br>

### Queue using arrays need to reindex when adding to beginning or removing from beginning
### Better to build with linked-list