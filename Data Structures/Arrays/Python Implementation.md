```python
class MyArray:
    def __init__(self):
        self.length = 0
        self.data = []

    def __str__(self):
        return f"data: {self.data}, length: {self.length}"

    def get(self, index):
        return self.data[index]

    def push(self, item):
        self.data.insert(self.length, item)
        self.length += 1

    def pop(self):
        if self.length == 0:
            return None
        last_item = self.data[(self.length - 1)]
        self.data.pop((self.length - 1))
        self.length -= 1
        return last_item

    def delete(self, index):
        item = self.data[index]
        self.shift_items(index)
        
    def shift_items(self, index):
        for i in range(index, self.length -1):
            self.data[i] = self.data[i+1]
        self.data.pop(self.length - 1)
        self.length -= 1        

    def get_length(self):
        return self.length
```