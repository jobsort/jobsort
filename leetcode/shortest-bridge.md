# Shortest Bridge Problem & Solution

See the [shortest bridge problem on LeetCode](https://leetcode.com/problems/shortest-bridge).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int shortestBridge(vector<vector<int>>& grid) {

    // O(n^2)
    for (int i = 0; i < grid.size(); ++i) {
      for (int j = 0; j < grid[i].size(); ++j) {
        if (grid[i][j] == 1) {
          dfs(grid, i, j);
          goto skip; // breaks out of two nested loops
        }
      }
    }

    skip:
    int result = 0;
    queue<pair<int, int>> q;

    // O(n^2)
    for (int i = 0; i < grid.size(); ++i) {
      for (int j = 0; j < grid[i].size(); ++j) {
        if (grid[i][j] == 2) {
          q.push({i, j});
        }
      }
    }

    // O(n^2)
    while (!q.empty()) {
      queue<pair<int, int>> q2;
      while (!q.empty()) {
        auto [i, j] = q.front(); q.pop();

        for (auto [ii, jj] : vector<pair<int, int>>{{i + 1, j}, {i - 1, j}, {i, j + 1}, {i, j - 1}}) {
          if (ii >=0 && ii < grid.size() && jj >= 0 && jj < grid.size()) {
            if (grid[ii][jj] == 1) {
              return result;
            } else if (grid[ii][jj] == 0) {
              grid[ii][jj] = -1;
              q2.push({ii, jj});
            }
          }
        }
      }

      q = q2;
      result++;
    }

    return result; // noop
  }

private:
  void dfs(vector<vector<int>>& grid, int i, int j) {
    grid[i][j] = 2;
    
    if (i > 0 && grid[i - 1][j] == 1) { dfs(grid, i - 1, j); }
    if (j > 0 && grid[i][j - 1] == 1) { dfs(grid, i, j - 1); }
    if (i < grid.size() - 1 && grid[i + 1][j] == 1) { dfs(grid, i + 1, j); }
    if (j < grid.size() - 1 && grid[i][j + 1] == 1) { dfs(grid, i, j + 1); }
  }
};
```
