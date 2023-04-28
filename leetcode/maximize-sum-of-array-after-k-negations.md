---
name: "Maximize Sum of Array after K Negations"
title: "LeetCode Maximize Sum of Array after K Negations Solution"
description: "Solution for given an integer array nums and an integer k, modify the array in the following way: choose an index i and replace nums[i] with -nums[i]. You should apply this process exactly k times. You may choose the same index i multiple times. Return the largest possible sum of the array after modifying it in this way."
published: "2021-12-16 PDT"
modified: "2021-12-16 PDT"
---

# Maximize Sum of Array after K Negations Problem & Solution

Given an integer array `nums` and an integer `k`, modify the array in the following way: choose an index `i` and replace `nums[i]` with `-nums[i]`.

You should apply this process exactly `k` times.
You may choose the same index `i` multiple times.

Return the largest possible sum of the array after modifying it in this way.

See the [maximize sum of array after k negations problem on LeetCode](https://leetcode.com/problems/maximize-sum-of-array-after-k-negations).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int largestSumAfterKNegations(vector<int>& nums, int k) {
    for (int i = 0; i < k; ++i) {
      int lowest = numeric_limits<int>::max();
      int jj = -1;
      for (int j = 0; j < nums.size(); ++j) {
        if (lowest > nums[j]) {
          lowest = nums[j];
          jj = j;
        }
      }

      nums[jj] *= -1;
    }

    int sum = 0;
    for (int i = 0; i < nums.size(); ++i) {
      sum += nums[i];
    }

    return sum;
  }
};
```
