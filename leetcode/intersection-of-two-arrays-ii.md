---
name: "Intersection of Two Arrays II"
title: "LeetCode Intersection of Two Arrays II Solution"
description: "Solution for the intersection of two arrays ii problem from LeetCode."
published: "2021-07-09 PDT"
modified: "2021-07-09 PDT"
---

# Intersection of Two Arrays II Problem & Solution

Given two integer arrays `nums1` and `nums2`, return an array of their intersection.
Each element in the result must appear as many times as it shows in both arrays and you may return the result in any order.

See the [intersection of two arrays ii problem on LeetCode](https://leetcode.com/problems/intersection-of-two-arrays-ii).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> intersect(vector<int>& nums1, vector<int>& nums2) {
    vector<int> usage1(1001, 0);
    vector<int> usage2(1001, 0);

    for (int i = 0; i < nums1.size(); ++i) {
      ++usage1[nums1[i]];
    }

    for (int i = 0; i < nums2.size(); ++i) {
      ++usage2[nums2[i]];
    }

    vector<int> result;

    for (int i = 0; i < 1001; ++i) {
      if (usage1[i] > 0 && usage2[i] > 0) {
        for (int j = 0; j < min(usage1[i], usage2[i]); ++j) {
          result.push_back(i);
        }
      }
    }

    return result;
  }
};
```
