# Number of Equivalent Domino Pairs Problem & Solution

See the [number of equivalent domino pairs problem on LeetCode](https://leetcode.com/problems/number-of-equivalent-domino-pairs).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int numEquivDominoPairs(vector<vector<int>>& dominoes) {
    unordered_map<int, int> freq;
    for (auto domino : dominoes) {
      int k = domino[0] < domino[1]
        ? domino[0] * 10 + domino[1]
        : domino[1] * 10 + domino[0];

      ++freq[k];
    }

    int result = 0;
    for (auto [k, v] : freq) {

      // factorial(v) / (factorial(2) * factorial(v - 2));
      result += v * (v - 1) / 2;
    }

    return result;
  }
};
```
