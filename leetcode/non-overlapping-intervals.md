# Non-overlapping Intervals Problem & Solution

See the [non-overlapping intervals problem on LeetCode](https://leetcode.com/problems/non-overlapping-intervals).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int eraseOverlapIntervals(vector<vector<int>>& intervals) {
    sort(intervals.begin(), intervals.end());

    int j = 0, result = 0;
    for (int i = 1; i < intervals.size(); ++i) {
      if (intervals[j][1] > intervals[i][0]) {
        ++result;

        // Picks the new `j` to be the one with the lowest end interval.
        if (intervals[j][1] > intervals[i][1]) {
          j = i;
        }
      } else {
        j = i;
      }
    }

    return result;
  }
};
```
