---
name: "Excel Sheet Column Title"
title: "LeetCode Excel Sheet Column Title Solution"
description: "Solution for the Excel sheet column title problem from LeetCode."
published: "2021-06-15 PDT"
modified: "2021-06-17 PDT"
---

# Excel Sheet Column Title Problem & Solution

Given an integer `columnNumber`, return its corresponding column title as it appears in an Excel sheet.

See the [Excel sheet column title problem on LeetCode](https://leetcode.com/problems/excel-sheet-column-title).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string convertToTitle(int columnNumber) {
    string result;

    while (columnNumber > 0) {

      // Must take into account the offset of the column number.
      --columnNumber;

      result += columnNumber % 26 + 'A';
      columnNumber /= 26;
    }

    reverse(result.begin(), result.end());

    return result;
  }
};
```
