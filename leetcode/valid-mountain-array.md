---
name: "Valid Mountain Array"
title: "LeetCode Valid Mountain Array Solution"
description: "Solution for given an array of integers arr, return true if and only if it is a valid mountain array. Recall that arr is a mountain array if and only if: arr.length >= 3 There exists some i with 0 < i < arr.length - 1 such that: arr[0] < arr[1] < ... < arr[i - 1] < arr[i] arr[i] > arr[i + 1] > ... > arr[arr.length - 1]"
published: "2021-12-14 PDT"
modified: "2021-12-14 PDT"
---

# Valid Mountain Array Problem & Solution

Given an array of integers `arr`, return true if and only if it is a valid mountain array.

Recall that `arr` is a mountain array if and only if:

- `arr.length >= 3`
- There exists some `i` with `0 < i < arr.length - 1` such that:
  - `arr[0] < arr[1] < ... < arr[i - 1] < arr[i]`
  - `arr[i] > arr[i + 1] > ... > arr[arr.length - 1]`

See the [valid mountain array problem on LeetCode](https://leetcode.com/problems/valid-mountain-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool validMountainArray(vector<int>& arr) {
    if (arr.size() < 3) {
      return false;
    }

    int i = 1;
    while (i < arr.size() && arr[i - 1] < arr[i]) {
      ++i;
    }

    if (i == 1 || i == arr.size()) {
      return false;
    }

    while (i < arr.size() && arr[i - 1] > arr[i]) {
      ++i;
    }

    return i == arr.size();
  }
};
```
