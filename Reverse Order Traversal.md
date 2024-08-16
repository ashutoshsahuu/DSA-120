# Reverse Array Traversal

## Problem Description

You are given an array, stored in a variable with the name `arr`. The size of the array is stored in a variable with the name `size`. You have to print the reverse traversal of the array.

For example, consider the value stored in `size = 4`, and the array is `arr = [1 2 3 4]`. Then, the required output will be:


## Input Description

### Input Format
- The first line of the input contains the value stored in `size`.
- The next line of the input contains the values stored in the array. All the values are on a single line separated by space.

## Output Description

### Output Format
- You have to print the reverse traversal of the array, as shown in the problem statement.

## Example Input/Output

### Input:
```
5
1 2 3 4 5
```

### Output :
```
5 4 3 2 1
```

## Solution Code Python

```
def reverseArray(arr, n):
    i = 0
    for i in range(n//2):
        arr[i], arr[n-i-1] = arr[n-i-1], arr[i]
  
    return ' '.join(map(str, arr))

n = int(input())
arr = list(map(int, input().split()))
res = reverseArray(arr, n)
print(res)

```