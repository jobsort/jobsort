---
name: "Check if N and its Double Exist"
title: "LeetCode Check if N and its Double Exist Solution"
description: "Solution for the check if n and its double exist problem from LeetCode."
published: "2023-01-02 PDT"
modified: "2023-01-02 PDT"
---

# Check if N and its Double Exist Problem & Solution

See the [check if n and its double exist problem on LeetCode](https://leetcode.com/problems/check-if-n-and-its-double-exist).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool checkIfExist(vector<int>& arr) {
    sort(arr.begin(), arr.end());
    for (int i = 0; i < arr.size(); ++i) {
      if (arr[i] >= 0) {
        if (binary_search(arr.begin() + i + 1, arr.end(), 2 * arr[i])) {
          return true;
        }
      } else if (binary_search(arr.begin(), arr.begin() + i, 2 * arr[i])) {
        return true;
      }
    }

    return false;
  }
};
```
