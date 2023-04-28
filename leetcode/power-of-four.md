# Power of Four Problem & Solution

Given an integer `n`, return true if it is a power of four.
Otherwise, return false.

An integer `n` is a power of four, if there exists an integer x such that n == 4^x.

See the [power of four problem on LeetCode](https://leetcode.com/problems/power-of-four).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isPowerOfFour(int n) {

    // To be a power of 4, the number must:
    // 1. Have only one 1 in its binary representation.
    // 2. The number of trailing zeroes must be divisible by 2.
    return __builtin_popcount(n) == 1 && __builtin_ctz(n) % 2 == 0;
  }
};
```
