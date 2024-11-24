```javascript
class Node {
    constructor(value) {
        this.value = value;
        this.right = null;
        this.left = null;
    }
}

class BinarySearchTree {
    constructor() {
        this.root = null;
    }

    insert(value) {
        let newNode = new Node(value);
        if (!this.root) {
            this.root = newNode;
            return this;
        }
        else {
            let current = this.root
            while(true) {
                if (value === current.value) return undefined;
                if (value > current.value) {
                    if (current.right) current = current.right;
                    else {
                        current.right = newNode;
                        return this;
                    }
                } else if (value < current.value) {
                    if (current.left) current = current.left;
                    else {
                        current.left = newNode;
                        return this;
                    }
                }
            }
        }
    }

    search(value) {
        if (!this.root) return null;
        let current = this.root
        while(true) {
            if (current.value === value) return current;
            if (value < current.value) {
                if (!current.left) return null;
                current = current.left;
            } else {
                if (!current.right) return null;
                current = current.right;
            }
        }
    }
    
}
```