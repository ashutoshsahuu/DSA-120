# Rotate the Array Returns Back

## Description

You are given an array of `n` elements and an integer `k`. You need to rotate the array by `k` units.

## Input Description

- The first line contains `t`, the number of test cases.
- For each test case:
  - The first line has `n` (the number of elements in the array) and `k` (the number of times the array has to be rotated).
  - The second line contains `n` integers representing the elements of the array.

## Constraints

- 1 ≤ T ≤ 20
- 1 ≤ N ≤ 50000
- 0 ≤ K ≤ 1000000000
- 1 ≤ Ai ≤ 1000000

## Output Description

For each test case, output `N` elements of the array, rotated by `K` units.

## Sample Input 1

```
3
2 1
1 2
2 2
1 2
3 1
1 2 3

```

## Sample Output
```
2 1
1 2
3 1 2
```

## Solution Code Python

```
def rotateArray(arr , k , n):
  k = k % n
  return arr[-k:] + arr[:-k]
  
tc = int(input())
for _ in range(tc):
  n , k = map(int , input().split())
  arr = list(map(int , input().split()))
  res = rotateArray(arr , k , n)
  print(*res)

```