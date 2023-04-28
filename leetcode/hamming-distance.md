# Hamming Distance Problem & Solution

The Hamming distance between two integers is the number of positions at which the corresponding bits are different.
Given two integers `x` and `y`, return the Hamming distance between them.

See the [Hamming distance problem on LeetCode](https://leetcode.com/problems/hamming-distance).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int hammingDistance(int x, int y) {
    return __builtin_popcount(x ^ y);
  }
};
```
