```javascript
class MaxBinaryHeap {
    constructor() {
        this.values = [];
    }

    insert(value) {
        let heap = this.values;
        heap.push(value);
        let index = heap.length - 1;
        let parentIndex = (index-1)/2 | 0;
        while (value > heap[parentIndex]) {
            [heap[index], heap[parentIndex]] = [heap[parentIndex], heap[index]];
            index = parentIndex;
            parentIndex = (index-1)/2 | 0;
        }
    }

    extractMax() {
        let heap = this.values;
        if (!heap.length) return undefined;
        [heap[0], heap[heap.length - 1]] = [heap[heap.length - 1], heap[0]];
        let maxValue = heap.pop();
        let element = heap[0];
        let index = 0;

        while (true) {
            let leftChildIdx = (2 * index) + 1;
            let rightChildIdx = (2 * index) + 2;
            let leftChild, rightChild;
            let swap = null;

            if (leftChildIdx < heap.length) {
                leftChild = heap[leftChildIdx];
                if (leftChild > element) {
                    swap = leftChildIdx;
                }
            }
            if (rightChildIdx < heap.length) {
                rightChild = heap[rightChildIdx];
                if (rightChild > element && rightChild > leftChild) {
                    swap = rightChildIdx;
                }
            }
            if(swap === null) break;
            [heap[index], heap[swap]] = [heap[swap], heap[index]];
            index = swap;
        }
        return maxValue;
    }
}
```