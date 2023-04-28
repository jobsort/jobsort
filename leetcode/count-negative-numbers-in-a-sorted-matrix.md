# Count Negative Numbers in a Sorted Matrix Problem & Solution

See the [count negative numbers in a sorted matrix problem on LeetCode](https://leetcode.com/problems/count-negative-numbers-in-a-sorted-matrix).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int countNegatives(vector<vector<int>>& grid) {
    int count = 0;
    for (int i = 0; i < grid.size(); ++i) {
      for (int j = 0; j < grid[i].size(); ++j) {
        if (grid[i][j] < 0) {
          count += grid[i].size() - j;
          break;
        }
      }
    }

    return count;
  }
};
```
