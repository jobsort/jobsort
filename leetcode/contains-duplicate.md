---
name: "Contains Duplicate"
title: "LeetCode Contains Duplicate Solution"
description: "Solution for the contains duplicate problem from LeetCode."
published: "2021-06-29 PDT"
modified: "2021-06-29 PDT"
---

# Contains Duplicate Problem & Solution

Given an integer array `nums`, return true if any value appears at least twice in the array, and return false if every element is distinct.

See the [contains duplicate problem on LeetCode](https://leetcode.com/problems/contains-duplicate).

## C++ Solution

The runtime complexity of the algorithm is $O(n\log{}n)$.

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool containsDuplicate(vector<int>& nums) {
    sort(nums.begin(), nums.end());

    for (int i = 0; i < nums.size() - 1; ++i) {
      if (nums[i] == nums[i + 1]) {
        return true;
      }
    }

    return false;
  }
};
```
