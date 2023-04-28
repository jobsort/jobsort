# Shuffle String Problem & Solution

See the [shuffle string problem on LeetCode](https://leetcode.com/problems/shuffle-string).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string restoreString(string s, vector<int>& indices) {
    string result = s;

    for (int i = 0; i < indices.size(); ++i) {
      result[indices[i]] = s[i];
    }

    return result;
  }
};
```
