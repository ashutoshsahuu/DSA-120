# Product of Array Except Self

## Problem Description

Given an integer array `nums`, return an array `answer` such that `answer[i]` is equal to the product of all the elements of `nums` except `nums[i]`.

You must write an algorithm that:
- Runs in `O(n)` time.
- Does not use the division operation.
- Achieves `O(1)` extra space complexity (the output array does not count as extra space for space complexity analysis).

## Input Description

### Input Format
- The input consists of multiple test cases.
- The first line of input contains an integer `t` - the number of test cases.
- The following `2*t` lines contain the description of the `t` test cases.
  - The first line of each test case contains an integer `n` - the size of the array.
  - The second line of each test case contains `n` space-separated integers representing the array `nums`.

### Constraints:
- `1 <= t <= 10^3`
- `2 <= nums.length <= 10^5`
- `-30 <= nums[i] <= 30`

## Output Description

### Output Format
- For each test case, output `n` integers, where `n` is the size of the array for that test case.
- The `i-th` integer should be the product of the array except for the `i-th` element.

## Example Input/Output

### Input:

```
2
4
1 2 3 4
5
-1 1 0 3 -3
```
### Output:

```
24 12 8 6
0 0 9 0 0
```

# Code:

```
def productExceptSelf(arr , n):
  res = [1] * n
  
  lprod = 1
  for i in range(n):
    res[i] = lprod
    lprod *= arr[i]
    
  rprod = 1
  for i in range(n-1 , -1 , -1):
    res[i] *= rprod
    rprod *= arr[i]

  return res


tc = int(input())
for _ in range(tc):
  n = int(input())
  arr = list(map(int , input().split()))
  res = productExceptSelf(arr , n)
  print(*res)

```