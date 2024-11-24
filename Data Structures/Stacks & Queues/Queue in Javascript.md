```javascript
class Node {
    constructor(value) {
        this.value = value;
        this.next = null;
    }
}

class Queue {
    constructor() {
        this.first = null;
        this.last = null;
        this.size = 0;
    }

    enqueue(value) {
        let newNode = new Node(value)
        if (!this.first) {
            this.first = newNode;
            this.last = newNode;
        } else {
            this.last.next = newNode;
            this.last = newNode;
        }
        this.size++;
    }

    dequeue() {
        if (!this.first) return undefined;
        let node = this.first;
        if (this.size == 1) {
            this.last = null;
            this.first = null;
        } else {
            this.first = node.next;
            node.next = null;
        }
        this.size--;
        return node;
    }
    
}
```