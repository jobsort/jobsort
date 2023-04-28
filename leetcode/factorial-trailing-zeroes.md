# Factorial Trailing Zeroes Problem & Solution

Given an integer `n`, return the number of trailing zeroes in `n!`.

See the [factorial trailing zeroes problem on LeetCode](https://leetcode.com/problems/factorial-trailing-zeroes).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int trailingZeroes(int n) {
    int result = 0;

    // Sums up the powers of 5 at each step, skipping other factors than 5.
    while (n > 0) {
      result += n / 5;
      n /= 5;
    }

    return result;
  }
};
```
