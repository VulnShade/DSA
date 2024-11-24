## Queue
- in python utilize collections.deque
- double-ended queue
- O(1) popleft vs O(n) pop(0) for list
- append(), popleft()


### Number of calls within 3000 units of time
O(n)

```python
from collections import deque

class RecentCounter:
    def __init__(self):
        self.queue = deque()

    def ping(self, t: int) -> int:
        while self.queue and self.queue[0] < t - 3000:
            self.queue.popleft()
        
        self.queue.append(t)
        return len(self.queue)


# Your RecentCounter object will be instantiated and called as such:
# obj = RecentCounter()
# param_1 = obj.ping(t)
```