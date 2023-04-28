# Island Perimeter Problem & Solution

You are given row x col `grid` representing a map where `grid[i][j] = 1` represents land and `grid[i][j] = 0` represents water.

Grid cells are connected horizontally/vertically (not diagonally).
The grid is completely surrounded by water, and there is exactly one island (i.e., one or more connected land cells).

The island doesn't have "lakes", meaning the water inside isn't connected to the water around the island.
One cell is a square with side length 1.
The grid is rectangular, width and height don't exceed 100.
Determine the perimeter of the island.

See the [island perimeter problem on LeetCode](https://leetcode.com/problems/island-perimeter).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int islandPerimeter(vector<vector<int>>& grid) {
    int result = 0;

    // Iterates by row.
    for (int i = 0; i < grid.size(); ++i) {
      bool started = false;
      for (int j = 0; j < grid[i].size(); ++j) {
        if (!started && grid[i][j] == 1) {
          started = true;
          ++result;
        }

        if (started && (grid[i][j] == 0 || j == grid[i].size() - 1)) {
          started = false;
          ++result;
        }
      }
    }

    // Iterates by column.
    for (int j = 0; j < grid[0].size(); ++j) {
      bool started = false;
      for (int i = 0; i < grid.size(); ++i) {
        if (!started && grid[i][j] == 1) {
          started = true;
          ++result;
        }

        if (started && (grid[i][j] == 0 || i == grid.size() - 1)) {
          started = false;
          ++result;
        }
      }
    }

    return result;
  }
};
```
