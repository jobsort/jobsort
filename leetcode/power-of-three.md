# Power of Three Problem & Solution

Given an integer `n`, return true if it is a power of three.
Otherwise, return false.
An integer `n` is a power of three, if there exists an integer `x` such that `n == 3^x`.

See the [power of three problem on LeetCode](https://leetcode.com/problems/power-of-three).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isPowerOfThree(int n) {
    if (n <= 0) {
      return false;
    }

    // Represents the largest number that's a power of 3 and fits into a signed integer.
    int pow3_INT_MAX = pow(3, (int)(log10(INT_MAX) / log10(3)));

    return pow3_INT_MAX % n == 0;
  }
};
```
