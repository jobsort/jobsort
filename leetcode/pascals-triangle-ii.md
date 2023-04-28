---
name: "Pascal's Triangle II"
title: "LeetCode Pascal's Triangle II Solution"
description: "The solution for Pascal's triangle ii problem from LeetCode is to initialize the vector of vector of integers for the edge cases of rows equals 1 or 2, and then keep adding up the inner cells to construct the next row. And then swap the current row with the previous row."
published: "2021-06-08 PDT"
modified: "2021-06-09 PDT"
---

# Pascal's Triangle II Problem & Solution

Given an integer `rowIndex`, return the `rowIndex`th (0-indexed) row of the Pascal's triangle.
In Pascal's triangle, each number is the sum of the two numbers directly above it.

See [Pascal's triangle ii problem on LeetCode](https://leetcode.com/problems/pascals-triangle-ii).

## C++ Solution

First, we need to treat the edge cases where the `rowIndex` equals 0 or 1. Then, we only need to keep track of the current row and the previous row. There’s no point in keeping track of the entire triangle in memory as there’s no use for it. This saves memory. So, we construct the new row by summing up the inner cells of the previous row, and then we assign the current row to the previous row, and keep going till we calculate the row for the `rowIndex`.

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> getRow(int rowIndex) {
    if (rowIndex == 0) {
      return {1};
    }

    if (rowIndex == 1) {
      return {1, 1};
    }

    vector<int> result(rowIndex, 1);

    for (int i = 2; i <= rowIndex; ++i) {
      vector<int> tmp(i + 1, 1);
      for (int j = 1; j < i; ++j) {
        tmp[j] = result[j - 1] + result[j];
      }

      result = tmp;
    }

    return result;
  }
};
```
