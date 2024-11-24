## Bubble Sort
- Bubbles biggest item to end
- Then next biggest, etc
- O(n<sup>2</sup>)
- space complexity O(1)

```python
# Python
def bubble_sort(list):
    if not list:
        return None
    for index in range(len(list), 0, -1):
        i = 0
        j = 1
        while j < index:
            if list[i] > list[j]:
                temp = list[j]
                list[j] = list[i]
                list[i] = temp
            i += 1
            j += 1
    return list
```
<br>

```javascript
// javascript optimized
function bubbleSort(arr){
    let noSwaps;
    for (let i = arr.length; i > 0; i--) {
        noSwaps = true;
        for (let j = 0; j < i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                swap(arr, j, j + 1);
                noSwaps = false;
            }
        }
        if (noSwaps) break;
    }
    return arr;
}

function swap (arr, j, i) {
    [arr[j], arr[i]] = [arr[i], arr[j]];
}
```