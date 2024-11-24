```javascript
function mergeSort (arr) {
    if (arr.length <= 1) return arr;
    let half = arr.length / 2 | 0;
    return merge(mergeSort(arr.slice(0, half)), mergeSort(arr.slice(half)));
}

function merge (arr1, arr2) {
    let sorted = [];
    let i = 0;
    let j = 0;

    while (i < arr1.length && j < arr2.length) {
        if (arr1[i] < arr2[j]) {
            sorted.push(arr1[i]);
            i++;
        } else {
            sorted.push(arr2[j]);
            j++;
        }
    }
    while (i < arr1.length) {
        sorted.push(arr1[i]);
        i++;
        }
    while (j < arr2.length) {
        sorted.push(arr2[j]);
        j++;
    }
    return sorted;
}
```