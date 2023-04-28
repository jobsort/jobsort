---
name: "Sudoku Solver"
title: "LeetCode Sudoku Solver Solution"
description: "Solution for the sudoku solver problem from LeetCode."
published: "2023-02-08 PDT"
modified: "2023-02-08 PDT"
---

# Sudoku Solver Problem & Solution

See the [sudoku solver problem on LeetCode](https://leetcode.com/problems/sudoku-solver).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  void solveSudoku(vector<vector<char>>& board) {
    help(board);
  }

private:
  bool help(vector<vector<char>>& board) {
    for (int i = 0; i < 9; ++i) {
      for (int j = 0; j < 9; ++j) {
        if (board[i][j] == '.') {
          for (char c = '1'; c <= '9'; ++c) {
            if (valid(board, i, j, c)) {
              board[i][j] = c;

              if (help(board)) {
                return true;
              } else {
                board[i][j] = '.';
              }
            }
          }

          return false;
        }
      }
    }

    return true;
  }

  bool valid(vector<vector<char>>& board, int i, int j, char c) {
    for (int k = 0; k < 9; ++k) {
      if (board[i][k] == c) { return false; }
      if (board[k][j] == c) { return false; }
    }

    for (int ii = 0; ii < 3; ++ii) {
      for (int jj = 0; jj < 3; ++jj) {
        if (board[i / 3 * 3 + ii][j / 3 * 3 + jj] == c) { return false; }
      }
    }

    return true;
  }
};
```
