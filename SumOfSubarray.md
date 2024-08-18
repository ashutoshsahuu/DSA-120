# Sum of Subarray II

## Description

You are given an array of `N` integers and a single integer `K`. You need to find out if there is a subarray which has a sum exactly equal to `K`.

## Input Description

- The first line contains `T`, the number of test cases.
- For each test case:
  - The first line contains `N`, the size of the array, and `K`.
  - The second line contains `N` spaced integers, representing the elements of the array.

## Constraints

- 1 ≤ T ≤ 10
- 1 ≤ N ≤ 10^5
- 1 ≤ A[i] ≤ 10^12
- 1 ≤ K ≤ 10^12

## Output Description

For each test case, print "Yes" if there exists a subarray with sum `K`, otherwise print "No".

## Sample Input



```
3
5 3
1 2 1 3 4
4 5
1 2 1 3
3 2
1 2 1

```

## Sample Output
```
Yes
No
Yes
```

## Solution Code Python

```

def checkSubarraySum(arr, n, k):
    prefixSum = 0
    prefixSums = set()
    prefixSums.add(0)

    for num in arr:
        prefixSum += num

        if (prefixSum - k) in prefixSums:
            return "Yes"
        
        prefixSums.add(prefixSum)
    
    return "No"

t = int(input())
for _ in range(t):
    n, k = map(int, input().split())
    arr = list(map(int, input().split()))
    res = checkSubarraySum(arr, n, k)
    print(res)


```