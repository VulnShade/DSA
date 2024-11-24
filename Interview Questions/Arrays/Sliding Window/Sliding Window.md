## When to use Sliding Window:
1. Constraint metric - Sum, frequency, etc
2. numeric restriction on constraint metric
3. Find valid subarray in some way - longest, etc. 

### Examples:
- Find the longest subarray with a sum less than or equal to k
- Find the longest substring that has at most one "0"
- Find the number of subarrays that have a product less than k

### Algorithm:
- two vars: left, right
- initially left = right = 0 
- increase by increasing right
- if subarray becomes invalid, increase left