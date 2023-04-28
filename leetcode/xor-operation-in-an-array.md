# XOR Operation in an Array Problem & Solution

See the [XOR operation in an array problem on LeetCode](https://leetcode.com/problems/xor-operation-in-an-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,fast-math,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int xorOperation(int n, int start) {
    int result = 0;

    for (int i = 0; i < n; ++i) {
      result ^= start + 2 * i;
    }

    return result;
  }
};
```
