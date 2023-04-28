---
name: "Running Sum of 1D Array"
title: "LeetCode Running Sum of 1D Array Solution"
description: "Solution for the running sum of 1d array problem from LeetCode."
published: "2023-03-07 PDT"
modified: "2023-03-07 PDT"
---

# Running Sum of 1D Array Problem & Solution

See the [running sum of 1d array problem on LeetCode](https://leetcode.com/problems/running-sum-of-1d-array).

## C++ Solution

```cpp
class Solution {
public:
  vector<int> runningSum(vector<int>& nums) {
    for (int i = 1; i < nums.size(); ++i) {
      nums[i] += nums[i - 1];
    }

    return nums;
  }
};
```
