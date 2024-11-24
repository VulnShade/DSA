## 1. Start the pointers at the edges of the input. Move them towards each other until they meet.

```python 

# Example 1: Given a string s, return true if it is a palindrome, false otherwise.
# O(n)


def check_if_palindrome(s):
    left = 0
    right = len(s) - 1

    while left < right:
        if s[left] != s[right]:
            return False
        left += 1
        right -= 1
    
    return True

# Example 2 - O(n)

def sorted_two_sum(nums, target):
    i = 0
    j = len(nums) - 1
    while i < j:
        if i + j == target:
            return True
        elif i + j > target:
            j -= 1
        else:
            i += 1
    return False
        


print(sorted_two_sum([1, 2, 4, 6, 8, 14, 15], 13))

```
<br>

## 2. Move along both inputs simultaneously until all elements have been checked.
```python 
# Combine 2 sorted arrays into new sorted array - O(n)
def combine_sorted_arrays(arr1, arr2):
    i = 0
    j = 0
    combined = []
    while i < len(arr1) and j < len(arr2):
        if arr1[i] < arr2[j]:
            combined.append(arr1[i])
            i += 1
        else:
            combined.append(arr2[j])
            j += 1

    while i < len(arr1):
        combined.append(arr1[i])
        i += 1

    while j < len(arr2):
        combined.append(arr2[j])
        j += 1
    return combined


print(combine_sorted_arrays([1, 4, 7, 20], [3, 5, 6]))

#  return true if s is a subsequence of t - O(n)
def is_subsequence(str1, str2):
    i = 0
    j = 0
    while i < len(str1) and j < len(str2):
        if str1[i] == str2[j]:
            i += 1
        j += 1
    return i == len(str1)
     
```