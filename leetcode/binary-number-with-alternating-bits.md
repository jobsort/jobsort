# Binary Number with Alternating Bits Problem & Solution

Given a positive integer, check whether it has alternating bits: namely, if two adjacent bits will always have different values.

See the [binary number with alternating bits problem on LeetCode](https://leetcode.com/problems/binary-number-with-alternating-bits).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool hasAlternatingBits(int n) {
    int prev = n % 2;
    n /= 2;

    while (n > 0) {
      int mod = n % 2;
      n /= 2;

      if (mod == prev) {
        return false;
      }

      prev = mod;
    }

    return true;
  }
};
```
