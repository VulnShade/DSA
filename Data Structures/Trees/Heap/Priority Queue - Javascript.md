```javascript
class Node {
    constructor(value, priority){
        this.value = value;
        this.priority = priority;
    }
}

class PriorityQueue {
    constructor() {
        this.values = [];
    }

    enqueue(value, priority) {
        let queue = this.values;
        let newNode = new Node(value, priority);
        queue.push(newNode);
        let index = queue.length - 1;
        let parentIndex = (index-1)/2 | 0;
        while (newNode.priority < queue[parentIndex].priority) {
            [queue[index], queue[parentIndex]] = [queue[parentIndex], queue[index]];
            index = parentIndex;
            parentIndex = (index-1)/2 | 0;
        }
    }

    dequeue() {
        let queue = this.values;
        if (!queue.length) return undefined;
        [queue[0], queue[queue.length - 1]] = [queue[queue.length - 1], queue[0]];
        let highestPriority = queue.pop();
        let element = queue[0];
        let index = 0;

        while (true) {
            let leftChildIdx = (2 * index) + 1;
            let rightChildIdx = (2 * index) + 2;
            let leftChild, rightChild;
            let swap = null;

            if (leftChildIdx < queue.length) {
                leftChild = queue[leftChildIdx];
                if (leftChild.priority < element.priority) {
                    swap = leftChildIdx;
                }
            }
            if (rightChildIdx < queue.length) {
                rightChild = queue[rightChildIdx];
                if (rightChild.priority < element.priority && rightChild.priority < leftChild.priority) {
                    swap = rightChildIdx;
                }
            }
            if(swap === null) break;
            [queue[index], queue[swap]] = [queue[swap], queue[index]];
            index = swap;
        }
        return highestPriority;
    }
}
```