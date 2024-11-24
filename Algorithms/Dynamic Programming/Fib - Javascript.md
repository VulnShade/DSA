```javascript
// Recursion
function fibonacci(index, memo=[]) {
    if (memo[index] !== undefined) return memo[index];
    if (index <= 2) return 1;
    let res = fibonacci(index - 1) + fibonacci(index - 2);
    memo[index] = res;
    return res;
}


// Tabulation
function fibonacci(index) {
    if (index <= 2) return 1;
    var fibNums = [0, 1, 1]
    for (let i = 3; i <= index; i++) {
        fibNums[i] = fibNums[i-1] + fibNums[i-2];
    }
    return fibNums[index];
}
```