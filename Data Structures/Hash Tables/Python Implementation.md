```python
class HashTable:
    """Python hashtable"""

    def __init__(self, size):
        self.data = [None] * size
    
    def __str__(self):
        return str(self.data)

    def _hash(self, key):
        hash = 0
        for i in range(0, len(key)):
            hash = (hash + ord(key[i]) * i) % len(self.data)
        return hash
    
    def set(self, key, value):
        index = self._hash(key)
        if not self.data[index]:
            self.data[index] = []
        self.data[index].append([key, value])
        
    def get(self, key):
        index = self._hash(key)
        if self.data[index]:
            for item in self.data[index]:
                if item[0] == key:
                    return item[1]
            return None
       
    def keys(self):
        keysArray = []
        for i in range(0, len(self.data)):
            if self.data[i]:
                for item in self.data[i]:
                    keysArray.append(item[0])
        return(keysArray)
	```