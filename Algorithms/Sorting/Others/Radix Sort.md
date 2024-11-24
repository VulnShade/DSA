## Radix Sort
- Never makes comparisons
- Uses fact larger number has more digits
- Check right most digit and groups similar
- Reform list keeping those grouping order
- Repeat for each digit

Big O :
- Time - O(nk)
- Space - O(n + k)
n = length of array
k = digits(avg)

```javascript
// Javascript
function getDigit (num, digit) {
    num = (num / Math.pow(10, digit)) | 0;
    return num % 10;
}

function digitCount (num) {
    if (num === 0) return 1;
    return Math.floor(Math.log10(Math.abs(num))) + 1;
}

function mostDigits (arr) {
    let max = 0;
    for (num of arr) {
        max = Math.max(max, digitCount(num));
    }
    return max;
}

function radixSort (arr) {
    const maxDigits = mostDigits(arr);
    for (let i = 0; i < maxDigits; i++) {
        let digitBuckets = Array.from({ length: 10}, () => []);
        for(let j = 0; j < arr.length; j++) {
            let idx = getDigit(arr[j], i);
            digitBuckets[idx].push(arr[j]);
        }
        arr = [].concat(...digitBuckets);
    }
    return arr;
}
```