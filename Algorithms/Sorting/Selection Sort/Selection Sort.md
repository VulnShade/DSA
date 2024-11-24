## Selection Sort
- Scans list for smallest item
- Moves it to beginning
- O(n<sup>2</sup>) time
- space complexity O(1)
<br>

```python
# Python
def selection_sort(list):
    if not list:
        return None
    for i in range(0, len(list)):
        smallest = i
        for j in range(i+1, len(list)):
            if list[j] < list[smallest]:
                smallest = j
        temp = list[i]
        list[i] = list[smallest]
        list[smallest] = temp
    return list
```
<br>

```javascript
// Javascript optimized
function selectionSort(arr){
    for (let i = 0; i < arr.length; i++) {
        let min = i;
        for (let j = i + 1; j < arr.length; j++) {
            if (arr[min] > arr[j]) min = j;
        }
        if (i != min) swap(arr, min, i);
    }
    return arr;
}

function swap (arr, j, i) {
    [arr[j], arr[i]] = [arr[i], arr[j]];
}

```