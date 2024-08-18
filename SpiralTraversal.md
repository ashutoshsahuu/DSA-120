# Spiral Traversal (Rectangular Matrix)

## Description

You are given a matrix of size `N x M`. Print the spiral traversal of the matrix.

## Input Description

- The first line of the input contains `T`, the number of test cases.
- The first line of each test case contains `N` and `M`, the number of rows and columns in the given matrix.
- The next `N` lines contain `M` values each, denoting the elements of the matrix.

## Constraints

- 1 ≤ T ≤ 10
- 1 ≤ N, M ≤ 200
- 1 ≤ A[i][j] ≤ 200

## Output Description

For each test case, print the spiral traversal of the matrix, on a single line, on a new line.

## Sample Input 1

```
2
3 4
1 2 3 4
5 6 7 8
9 10 11 12
4 3
1 2 3
4 5 6
7 8 9
10 11 12

```

## Sample Output
```
1 5 9 10 11 12 8 4 3 2 6 7 
1 4 7 10 11 12 9 6 3 2 5 8 
```

## Solution Code Python

```

def vertical_spiral_traversal(mat, n, m):
    ans = []
    l, r, t, b = 0, m - 1, 0, n - 1

    while l <= r and t <= b:
  
      for i in range(t, b + 1):
        ans.append(mat[i][l])
      l += 1

      if t <= b:
        for i in range(l, r + 1):
          ans.append(mat[b][i])
        b -= 1

      if l <= r:
        for i in range(b, t - 1, -1):
          ans.append(mat[i][r])
        r -= 1

      if t <= b:
        for i in range(r, l - 1, -1):
          ans.append(mat[t][i])
        t += 1

    return ans

t = int(input())
for _ in range(t):
    n, m = map(int, input().split())
    mat = [list(map(int, input().split())) for _ in range(n)]
    res = vertical_spiral_traversal(mat, n, m)
    print(*res)

```