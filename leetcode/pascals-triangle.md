---
name: "Pascal's Triangle"
title: "LeetCode Pascal's Triangle Solution"
description: "The solution for Pascal's triangle problem from LeetCode is to initialize the vector of vector of integers for the edge cases of rows equals 1 or 2, and then keep adding up the inner cells to construct the next rows."
published: "2021-06-07 PDT"
modified: "2021-06-09 PDT"
---

# Pascal's Triangle Problem & Solution

Given an integer `numRows`, return the first numRows of Pascal's triangle.
In Pascal's triangle, each number is the sum of the two numbers directly above it.

See [Pascal's triangle problem on LeetCode](https://leetcode.com/problems/pascals-triangle).

## C++ Solution

First, you have to initialize the edge cases of rows equals 1 or 2. Second, you need to iterate from 3 all the way up to `numRows` and add up only the inner cells to construct each new row. Note that each new row is initialized with all 1s to avoid complicating the code. And then, only the inner cells are overwritten with the new values which depend on the previous row, specifically each new `row[j]` is the sum of `row[i - 1][j - 1]` and `row[i - 1][j]`. Note that in code we use `row[i - 2]` because the `i` index and `numRows` are off by one.

The runtime complexity of the algorithm is $O(n^2)$.

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> generate(int numRows) {
    if (numRows == 1) {
      return {{1}};
    }

    if (numRows == 2) {
      return {{1}, {1, 1}};
    }

    vector<vector<int>> result{{1}, {1, 1}};

    for (int i = 3; i <= numRows; ++i) {
      vector<int> row(i, 1);
      for (int j = 1; j < i - 1; ++j) {
        row[j] = result[i - 2][j - 1] + result[i - 2][j];
      }

      result.push_back(row);
    }

    return result;
  }
};
```
