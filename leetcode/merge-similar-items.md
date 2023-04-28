# Merge Similar Items Problem & Solution

See the [merge similar items problem on LeetCode](https://leetcode.com/problems/merge-similar-items).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> mergeSimilarItems(vector<vector<int>>& items1, vector<vector<int>>& items2) {
    map<int, int> m;
    for (int i = 0; i < items1.size(); ++i) {
      m[items1[i][0]] += items1[i][1];
    }
    for (int i = 0; i < items2.size(); ++i) {
      m[items2[i][0]] += items2[i][1];
    }

    vector<vector<int>> results;
    for (auto [k, v] : m) {
      results.push_back({k, v});
    }

    return results;
  }
};
```
