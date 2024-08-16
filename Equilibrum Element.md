
# Equilibrium Element

## Description:

Given an array A of N positive numbers. The task is to find the position where equilibriumfirstoccurs in the array. An equilibrium position in an array is a position such that the sum of elements before it is equal to the sum of elements after it. Thevalid index range is from [ 1, n-2 ]because there should be at least one element on both sides.

## Input Description : 

**Input Format :**

First Line has T ( Testcases) and then for every test case we have:

The first line contains an integer N denoting the size of the array.
Then in the following sequence are N space-separated values of the array A.
Constraints:

- 1 <= T <= 100
- 3 <= N <= 1000
- 1 <= Ai <= 10^8

## Outut Description : 

In a new line print the position at which the elements are at equilibrium if no equilibrium point exists print -1.

#### Sample Input

``` 
2 
5
15 1 5 5 5
3
1 2 3 
```

#### Sample Output
```
1
-1
```

# Python Code:

```
def equilibrium(arr , n):
  total_sum = sum(arr)
  left_sum = 0
  
  for i in range(1 , n-1):
    left_sum += arr[i-1]
    right_sum = total_sum - left_sum - arr[i]
    
    if right_sum == left_sum:
      return i
    
  return -1


tc = int(input())
for _ in range(tc):
  n = int(input())
  arr = list(map(int , input().split()))
  res = equilibrium(arr , n)
  print(res)
```

