```javascript
class Node {
    constructor (val) {
        this.val = val;
        this.next = null;
    }
}

class LinkedList {
    constructor () {
        this.head = null;
        this.tail = null;
        this.length = 0;
    }

    push(val) {
        let newNode = new Node(val);
        if (!this.head) {
            this.head = newNode;
            this.tail = newNode;
        } else {
            this.tail.next = newNode;
            this.tail = newNode;
        }
        this.length++;
        return this;
    }

    pop() {
        if (!this.head) return undefined;
        let node = this.head;
        if (node == this.tail) {
            let val = node.val;
            this.head = null;
            this.tail = null;
            this.length--;
            return val;
        }
        while(node.next != this.tail){
            node = node.next;
        }
        let returnNode = node.next;
        node.next = null;
        this.tail = node;
        this.length--;
        return returnNode;
    }

    shift() {
        if (!this.head) return undefined;
        let returnNode = this.head;
        this.head = this.head.next;
        if (!this.head) this.tail = this.head;
        this.length--;
        return returnNode;
    }

    unshift(val) {
        let newNode = new Node(val);
        if (!this.head) {
            this.head = newNode;
            this.tail = newNode;
        } else{
            newNode.next = this.head;
            this.head = newNode;
        }
        this.length++;
        return this;
    }

    get(idx) {
        if (idx < 0 || idx >= this.length) return null;
        let node = this.head;
        for (let i = 1; i <= idx; i++) {
            node = node.next
        }
        return node;
    }

    set(val, idx) {
        let node = this.get(idx);
        if (!node) return false;
        node.val = val;
        return true;
    }

    insert(val, idx) {
        if (idx < 0 || idx > this.length) return false;
        else if (idx == this.length) this.push(val);
        else if (idx == 0) this.unshift(val);
        else {
            let prev = this.get(idx - 1);
            let newNode = new Node(val);
            newNode.next = prev.next;
            prev.next = newNode;
            this.length++;
        }
        return true;
    }

    remove(idx) {
        let val = null;
        if (idx < 0 || idx >= this.length) return false;
        else if (idx == 0) return this.shift();
        else if (idx == this.length - 1) return this.pop();
        else {
            let prev = this.get(idx -1);
            node = prev.next;
            prev.next = prev.next.next;
            this.length--;
            return node;
        }

    }

    reverse() {
        let node = this.head;
        this.head = this.tail;
        this.tail = node;
        let prev = null;
        let next;
        for(let i = 0; i < this.length; i++) {
            next = node.next;
            node.next = prev;
            prev = node;
            node = next;
        }
        return this;
    }
}
```