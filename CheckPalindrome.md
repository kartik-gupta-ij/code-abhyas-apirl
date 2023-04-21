## Problem Statement

You are given a number n. You need to see if the number is a palindrome or not (recursively)

Example 1:

Input:
n = 100
Output: 0

Example 2:

Input:
n = 101
Output: 1

## Your Task

Complete the function `isPalin` that takes `n` as parameter and returns `true` or `false` . (In case of true, 1 will be printed by the driver code, otherwise 0)

## Constraints

* 1 <= n <= 108

## Expected Time Complexity

O(Log(N)).

## Expected Auxiliary Space

O(Log(N)) (Recursive).

### Naive Approach: Using Recursion

### C++

```cpp
// Recursive C++ program to check if a number is palindrome

#include<bits/stdc++.h>
using namespace std;

// Function to check if a number is palindrome
bool isPalin(int n, int &temp){
    if(n == 0){
        return true;
    }
    if(isPalin(n/10, temp) && (n % 10 == temp % 10)){
        temp /= 10;
        return true;
    }
    return false;
}

// Driver code
int main(){
    int n = 101;
    int temp = n;
    if(isPalin(n, temp)){
        cout << "1\n";
    }
    else{
        cout << "0\n";
    }
    return 0;
}
```
### Python

```py

def isPalin(n):
    # Convert the number to string and get the length
    s = str(n)
    l = len(s)
    
    # Base case: if the length is less than or equal to 1, it is a palindrome
    if l <= 1:
        return True
    
    # Compare the first and last characters, if they are not same, it is not a palindrome
    if s[0] != s[l-1]:
        return False
    
    # Recursively check if the string without the first and last characters is a palindrome
    return isPalin(s[1:l-1])

# Driver code
n = 101
if isPalin(n):
    print(1)
else:
    print(0)

```