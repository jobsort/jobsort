# Number of Islands Problem & Solution

See the [number of islands problem on LeetCode](https://leetcode.com/problems/number-of-islands).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int numIslands(vector<vector<char>>& grid) {
    int result = 1;
    for (int i = 0; i < grid.size(); ++i) {
      for (int j = 0; j < grid[i].size(); ++j) {
        if (grid[i][j] == '1') {
          ++result;

          help(grid, i, j);
        }
      }
    }

    return result - 1;
  }

private:
  void help(vector<vector<char>>& grid, int i, int j) {
    grid[i][j] = '2';
    
    vector<int> ii{0, 0, -1, 1}, jj{-1, 1, 0, 0};
    for (int k = 0; k < 4; ++k) {
      int iii = i + ii[k], jjj = j + jj[k];
      if (iii >= 0 && jjj >= 0 && iii < grid.size() && jjj < grid[iii].size() && grid[iii][jjj] == '1') {
        help(grid, iii, jjj);
      }
    }
  }
};
```
