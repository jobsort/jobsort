# Valid Sudoku Problem & Solution

See the [valid sudoku problem on LeetCode](https://leetcode.com/problems/valid-sudoku).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isValidSudoku(vector<vector<char>>& board) {
    for (int i = 0; i < 9; ++i) {
      vector<bool> seen(9);
      for (int j = 0; j < 9; ++j) {
        char c = board[i][j];
        if (c == '.') { continue; }
        if (seen[c - '1']) { return false; }

        seen[c - '1'] = true;
      }
    }

    for (int j = 0; j < 9; ++j) {
      vector<bool> seen(9);
      for (int i = 0; i < 9; ++i) {
        char c = board[i][j];
        if (c == '.') { continue; }
        if (seen[c - '1']) { return false; }

        seen[c - '1'] = true;
      }
    }

    for (int i = 0; i < 3; ++i) {
      for (int j = 0; j < 3; ++j) {
        vector<bool> seen(9);
        for (int k = 0; k < 3; ++k) {
          for (int l = 0; l < 3; ++l) {
            char c = board[i * 3 + k][j * 3 + l];
            if (c == '.') { continue; }
            if (seen[c - '1']) { return false; }

            seen[c - '1'] = true;
          }
        }
      }
    }

    return true;
  }
};
```
