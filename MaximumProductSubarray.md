# Maximum Product Subarray

## Description

Given an array `A` of size `n` consisting of positive and negative integers, find a subarray (containing at least one number) with the maximum product.

## Input Description

- The first line of the input contains one integer `t` (1 ≤ t ≤ 10) — the number of test cases. Then `t` test cases follow.
- The first line of each test case contains a single integer `n` (1 ≤ n ≤ 100000).
- The second line of the test case contains `n` integers (-100 ≤ Ai ≤ 100).

## Output Description

For each test case, print the answer: The maximum product possible.

## Sample Input

```
2
3
-3 0 -2
4
4 5 -1 2

```

## Sample Output
```
0
20
```

## Solution Code Python

```

def maxProductSubarray(arr , n):
  maxi = arr[0]
  currMax = arr[0]
  currMin = arr[0]
  
  for i in range(1 , n):
    if arr[i] < 0:
      currMax , currMin = currMin , currMax
    
    currMax = max(arr[i] , currMax*arr[i])
    currMin = min(arr[i] , currMin*arr[i])
    
    maxi = max(maxi , currMax)
  
  return maxi


tc = int(input())
for _ in range(tc):
  n = int(input())
  arr = list(map(int , input().split()))
  res = maxProductSubarray(arr , n)
  print(res)

```