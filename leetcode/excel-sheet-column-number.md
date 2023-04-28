---
name: "Excel Sheet Column Number"
title: "LeetCode Excel Sheet Column Number Solution"
description: "Solution for given a string columnTitle that represents the column title as appears in an Excel sheet, return its corresponding column number."
published: "2021-06-16 PDT"
modified: "2021-08-01 PDT"
---

# Excel Sheet Column Number Problem & Solution

Given a string `columnTitle` that represents the column title as appears in an Excel sheet, return its corresponding column number.

See the [Excel sheet column number problem on LeetCode](https://leetcode.com/problems/excel-sheet-column-number).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int titleToNumber(string columnTitle) {
    int result = 0;

    for (int i = 0; i < columnTitle.size(); ++i) {

      // The parentheses to calculate the digits are used to avoid overflow.
      result = result * 26 + (columnTitle[i] - 'A' + 1);
    }

    return result;
  }
};
```
