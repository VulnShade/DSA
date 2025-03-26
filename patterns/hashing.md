# Hashing 

## Checking for existence
<div style="background-color:rgb(219, 216, 216); border-left: 4px solid #ccc; padding: 10px; color: black">
<b>Example: Given an array of integers nums and an integer target, return indices of two numbers such that they add up to target. You cannot use the same index twice. </b>
</div>

```python
def twoSum(self, nums: List[int], target: int) -> List[int]:
    dic = {}
    for i in range(len(nums)):
        num = nums[i]
        complement = target - num
        if complement in dic: # This operation is O(1)!
            return [i, dic[complement]]
        
        dic[num] = i
    
    return [-1, -1]
```

- Time complexity: O(n) 
- Space complexity: O(n)
<br>

## Counting
<div style="background-color:rgb(219, 216, 216); border-left: 4px solid #ccc; padding: 10px; color: black">
<b>Example: You are given a string s and an integer k. Find the length of the longest substring that contains at most k distinct characters.</b>

<br>

For example, given s = "eceba" and k = 2, return 3. The longest substring with at most 2 distinct characters is "ece".
</div>

```python
from collections import defaultdict

def find_longest_substring(s, k):
    counts = defaultdict(int)
    left = ans = 0
    for right in range(len(s)):
        counts[s[right]] += 1
        while len(counts) > k:
            counts[s[left]] -= 1
            if counts[s[left]] == 0:
                del counts[s[left]]
            left += 1
        
        ans = max(ans, right - left + 1)
    
    return ans
```
- Time complexity: O(n) 
- Space complexity: O(k)

### Counter One Liner:
```python
from collections import Counter

def areOccurrencesEqual(self, s: str) -> bool:
    return len(set(Counter(s).values())) == 1

```

## Number of subarrays with exact constraint
<div style="background-color:rgb(219, 216, 216); border-left: 4px solid #ccc; padding: 10px; color: black">
<b>Given an integer array nums and an integer k, find the number of subarrays whose sum is equal to k.</b>
</div>

```python
from collections import defaultdict

class Solution:
    def subarraySum(self, nums: List[int], k: int) -> int:
        counts = defaultdict(int)
        counts[0] = 1
        ans = curr = 0

        for num in nums:
            curr += num
            ans += counts[curr - k]
            counts[curr] += 1
    
        return ans
```