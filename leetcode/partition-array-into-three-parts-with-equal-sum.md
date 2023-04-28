---
name: "Partition Array into Three Parts with Equal Sum"
title: "LeetCode Partition Array into Three Parts with Equal Sum Solution"
description: "Solution for the partition array into three parts with equal sum problem from LeetCode."
published: "2022-12-08 PDT"
modified: "2022-12-08 PDT"
---

# Partition Array into Three Parts with Equal Sum Problem & Solution

See the [partition array into three parts with equal sum problem on LeetCode](https://leetcode.com/problems/partition-array-into-three-parts-with-equal-sum).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool canThreePartsEqualSum(vector<int>& arr) {
    int total = 0;
    for (int i = 0; i < arr.size(); ++i) {
      total += arr[i];
    }

    int i, left = 0;
    for (i = 0; i < arr.size() - 1; ++i) {
      left += arr[i];
      if (left * 2 == total - left) {
        break;
      }
    }

    int j, right = 0;
    for (j = arr.size() - 1; j > 0; --j) {
      right += arr[j];
      if (right * 2 == total - right) {
        break;
      }
    }

    return i + 1 < j && left == right;
  }
};
```
