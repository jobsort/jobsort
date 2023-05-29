# Arranging Coins Problem & Solution

See the [arranging coins problem on LeetCode](https://leetcode.com/problems/arranging-coins).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int arrangeCoins(int n) {
    // n * (n + 1) / 2 is the sum of an arithmetic progression
    int i, j;
    for (i = j = 1; (long)i * (i + 1) / 2 <= n; j = i++) {
      // noop
    }

    return j;
  }
};
```
