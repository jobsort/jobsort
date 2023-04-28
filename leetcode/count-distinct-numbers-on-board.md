# Count Distinct Numbers on Board Problem & Solution

See the [count distinct numbers on board problem on LeetCode](https://leetcode.com/problems/count-distinct-numbers-on-board).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int distinctIntegers(int n) {
    if (n == 1) {
      return 1;
    }

    return n - 1;
  }
};
```
