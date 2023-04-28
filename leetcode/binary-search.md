---
name: "Binary Search"
title: "LeetCode Binary Search Solution"
description: "Solution for given an array of integers nums which is sorted in ascending order, and an integer target, write a function to search target in nums. If target exists, then return its index. Otherwise, return -1. You must write an algorithm with O(log n) runtime complexity."
published: "2021-08-18 PDT"
modified: "2021-08-18 PDT"
---

# Binary Search Problem & Solution

Given an array of integers `nums` which is sorted in ascending order, and an integer `target`, write a function to search `target` in `nums`.
If `target` exists, then return its index.
Otherwise, return -1.

You must write an algorithm with $O(\log{}n)$ runtime complexity.

See the [binary search problem on LeetCode](https://leetcode.com/problems/binary-search).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int search(vector<int>& nums, int target) {
    int low = 0;
    int high = nums.size() - 1;
    while (low < high) {

      // Uses this way of calculating the midpoint vs. `(low + high) / 2` to avoid overflow.
      int mid = low + (high - low) / 2;
      if (target > nums[mid]) {
        low = mid + 1;
      } else {
        high = mid;
      }
    }

    return target == nums[low] ? low : -1;
  }
};
```
