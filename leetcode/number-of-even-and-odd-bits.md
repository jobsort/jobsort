# Number of Even and Odd Bits Problem & Solution

See the [number of even and odd bits problem on LeetCode](https://leetcode.com/problems/number-of-even-and-odd-bits).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> evenOddBit(int n) {
    int i = 0, even = 0, odd = 0;
    while (n > 0) {
      if (n % 2 == 1) {
        if (i % 2 == 0) {
          ++even;
        } else {
          ++odd;
        }
      }

      ++i;
      n /= 2;
    }

    return {even, odd};
  }
};
```
