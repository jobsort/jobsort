---
name: "Range Sum Query Immutable"
title: "LeetCode Range Sum Query Immutable Solution"
description: "Solution for given an integer array nums, handle multiple queries of the following type: Calculate the sum of the elements of nums between indices left and right inclusive where left <= right. Implement the NumArray class: NumArray(int[] nums) Initializes the object with the integer array nums. int sumRange(int left, int right) Returns the sum of the elements of nums between indices left and right inclusive (i.e. nums[left] + nums[left + 1] + ... + nums[right])."
published: "2021-07-18 PDT"
modified: "2021-08-19 PDT"
---

# Range Sum Query Immutable Problem & Solution

Given an integer array `nums`, handle multiple queries of the following type:

Calculate the sum of the elements of nums between indices `left` and `right` inclusive where `left <= right`.

Implement the `NumArray` class:

- `NumArray(int[] nums)` Initializes the object with the integer array nums.
- `int sumRange(int left, int right)` Returns the sum of the elements of `nums` between indices `left` and `right` inclusive (i.e. `nums[left] + nums[left + 1] + ... + nums[right]`).

See the [range sum query immutable problem on LeetCode](https://leetcode.com/problems/range-sum-query-immutable).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

/**
 * Your NumArray object will be instantiated and called as such:
 * NumArray* obj = new NumArray(nums);
 * int param_1 = obj->sumRange(left,right);
 */
class NumArray {
public:
  NumArray(vector<int>& nums) {
    sums = vector<int>(nums.size() + 1, 0);
    for (int i = 0; i < nums.size(); ++i) {
      sums[i + 1] = sums[i] + nums[i];
    }
  }

  int sumRange(int left, int right) {
    return sums[right + 1] - sums[left];
  }

private:
  vector<int> sums;
};
```
