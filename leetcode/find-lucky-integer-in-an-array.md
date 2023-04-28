# Find Lucky Integer in an Array Problem & Solution

See the [find lucky integer in an array problem on LeetCode](https://leetcode.com/problems/find-lucky-integer-in-an-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int findLucky(vector<int>& arr) {
    unordered_map<int, int> freq;
    for (auto a : arr) {
      ++freq[a];
    }

    int result = -1;
    for (auto [k, v] : freq) {
      if (k == v) {
        result = max(result, v);
      }
    }

    return result;
  }
};
```
