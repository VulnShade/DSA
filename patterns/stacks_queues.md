# Stacks & Queues

> Use Dynamic Arrays
```python
stack = []

# Add to stack
stack.append(<item>)

# Pop stack
stack.pop()
```


## String Problems:

<div style="background-color:rgb(219, 216, 216); border-left: 4px solid #ccc; padding: 10px; color: black">
<b>Example: Remove All Adjacent Duplicates In String.</b>
<p>You are given a string s. Continuously remove duplicates (two of the same character beside each other) until you can't anymore. Return the final string after this.

For example, given s = "abbaca", you can first remove the "bb" to get "aaca". Next, you can remove the "aa" to get "ca". This is the final answer. </p>
</div>

```python
def removeDuplicates(s):
        stack = []
        for c in s:
            if stack and stack[-1] == c:
                stack.pop()
            else:
                stack.append(c)
        
        return "".join(stack)
```

<br> 
<hr>

## Queues 
> Use deque

```python
import collection
queue = collection.deque()

# Enqueue
queue.append(<item>)

# Dequeue
queue.popleft()
```

### Monotonic
>(of a function or quantity) varying in such a way that it either never decreases or never increases.
```python
Given an integer array nums

stack = []
for num in nums:
    while stack.length > 0 AND stack.top >= num:
        stack.pop()
    // Between the above and below lines, do some logic depending on the problem
    stack.push(num)
```

<br>

<div style="background-color:rgb(219, 216, 216); border-left: 4px solid #ccc; padding: 10px; color: black">
Given an array of integers temperatures that represents the daily temperatures, return an array answer such that answer[i] is the number of days you have to wait after the ith day to get a warmer temperature. If there is no future day that is warmer, have answer[i] = 0 instead.
</div>

```python
def dailyTemperatures(=temperatures) :
    stack = []
    answer = [0] * len(temperatures)
    
    for i in range(len(temperatures)):
        while stack and temperatures[stack[-1]] < temperatures[i]:
            j = stack.pop()
            answer[j] = i - j
        stack.append(i)
    
    return answer
```

<br>
<div style="background-color:rgb(219, 216, 216); border-left: 4px solid #ccc; padding: 10px; color: black">
<b>Example: Longest Continuous Subarray With Absolute Diff Less Than or Equal to Limit</b>
Given an array of integers nums and an integer limit, return the size of the longest subarray such that the absolute difference between any two elements of this subarray is less than or equal to limit.
</div>

```python
def maxSlidingWindow(nums, k)
    ans = []
    queue = deque()
    for i in range(len(nums)):
        # maintain monotonic decreasing.
        # all elements in the deque smaller than the current one
        # have no chance of being the maximum, so get rid of them
        while queue and nums[i] > nums[queue[-1]]:
            queue.pop()

        queue.append(i)

        # queue[0] is the index of the maximum element.
        # if queue[0] + k == i, then it is outside the window
        if queue[0] + k == i:
            queue.popleft()
        
        # only add to the answer once our window has reached size k
        if i >= k - 1:
            ans.append(nums[queue[0]])

    return ans
```
