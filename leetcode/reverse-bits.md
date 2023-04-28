# Reverse Bits Problem & Solution

Reverse bits of a given 32 bits unsigned integer.

See the [reverse bits problem on LeetCode](https://leetcode.com/problems/reverse-bits).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  uint32_t reverseBits(uint32_t n) {
    uint32_t result = 0;

    for (int i = 0; i < sizeof(n) * /*bits=*/8; ++i) {
      result |= n & 1;
      n = n >> 1;

      // Shifts the result to the left 31 instead of 32 times.
      if (i < sizeof(n) * /*bits=*/8 - 1) {
        result = result << 1;
      }
    }

    return result;
  }
};
```
