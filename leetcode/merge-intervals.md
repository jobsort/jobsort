# Merge Intervals Problem & Solution

See the [merge intervals problem on LeetCode](https://leetcode.com/problems/merge-intervals).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> merge(vector<vector<int>>& intervals) {
    sort(intervals.begin(), intervals.end());

    vector<vector<int>> results;

    int i = 0;
    while (i < intervals.size()) {
      int j = i + 1;
      while (j < intervals.size() &&
          intervals[j][0] <= intervals[i][1]) {
        intervals[i][1] = max(intervals[i][1], intervals[j][1]);

        ++j;
      }

      results.push_back(intervals[i]);

      i = j;
    }

    return results;
  }
};
```
