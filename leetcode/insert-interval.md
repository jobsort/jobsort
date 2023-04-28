# Insert Interval Problem & Solution

See the [insert interval problem on LeetCode](https://leetcode.com/problems/insert-interval).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> insert(vector<vector<int>>& intervals, vector<int>& newInterval) {
    auto it = lower_bound(intervals.begin(), intervals.end(), newInterval);

    it = intervals.insert(it, newInterval); // O(n)
    if (it != intervals.begin()) {
      --it;
    }

    int j = 0;
    while (j < 2 && it < intervals.end()) {
      int i = 1;
      while (it + i < intervals.end() && (*it)[1] >= (*(it + i))[0]) {
        (*it)[1] = max((*it)[1], (*(it + i))[1]);
        ++i;
      }

      it = intervals.erase(it + 1, it + i); // O(n)
      ++j;
    }

    return intervals;
  }
};
```
