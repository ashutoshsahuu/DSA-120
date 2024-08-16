
# Check Palindrome

## Description:

You are given a string, whose size is stored in a variable with the name **N** 
The string is stored in a variable with the name **str**
Print **Yes**, if the string is a palindrome, else print **No**
For example, consider the value stored in **str = "naman"**, if we reverse the string, the reversed string will be the same as the original string, hence the string is considered as palindrome, therefore, the output is **Yes**

#### Note : A palindrome is a string which is the same read forwards or backwards

## Input Description : 

**Input Format :**

The first line of the input contains the value stored in **N** .
The next line of the input contains the value stored instr

## Outut Description : 

Print **Yes**, if the string stored instris a palindrome, else print **No**

#### Sample Input

``` 
madam
```

#### Sample Output
```
Yes
```

# Python Code:

```
def palindromCheck(s ,n):
  rev = s[::-1]
  
  return rev == s
  
n = int(input())
s = input()
res = palindromCheck(s ,  n)
if res:
  print('Yes')
else:
  print('No')

```
**Detect Palindrom in Number**

```
n = int(input())
rev = 0
m = n
while n:
  rem = n % 10
  n = n // 10
  rev = rev * 10 + rem

if rev == m:
  print('Yes')
else:
  print('No')
```

