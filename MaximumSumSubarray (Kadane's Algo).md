# Maximum Sum Subarray (Kadane's Algorithm)

## Description

You are given an array of integers of size `N`. You need to find and print the maximum sum of a contiguous subarray (containing at least one integer) from this array.

## Input Description

- The first line contains `T`, the number of test cases.
- For each test case:
  - The first line contains `N`, the size of the array.
  - The second line contains `N` spaced integers.

## Constraints

- 1 ≤ T ≤ 10
- 1 ≤ N ≤ 10^6
- -10^6 ≤ A[i] ≤ 10^6

## Output Description

For each test case, print the maximum sum of the contiguous subarray on a new line.

## Sample Input

```
2
5
1 2 0 4 5
5
3 -4 1 2 -1

```

## Sample Output
```
12
3
```

## Solution Code Python

```
def MaxSumSubarray(arr , n):
  cMax = arr[0]
  maxi = arr[0]
  
  for i in range(1 , n):
    cMax = max(arr[i] , cMax + arr[i])
    maxi = max(maxi , cMax)
  
  return maxi


tc = int(input())
for _ in range(tc):
  n = int(input())
  arr = list(map(int , input().split()))
  res = MaxSumSubarray(arr , n)
  print(res)


```