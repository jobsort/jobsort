# Counting Bits Problem & Solution

Given an integer `n`, return an array `ans` of length `n + 1` such that for each `i (0 <= i <= n)`, `ans[i]` is the number of 1's in the binary representation of `i`.

See the [counting bits problem on LeetCode](https://leetcode.com/problems/counting-bits).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> countBits(int n) {
    vector<int> results(n + 1, 0);

    for (int i = 1; i < results.size(); ++i) {
      results[i] = __builtin_popcount(i);
    }

    return results;
  }
};
```
