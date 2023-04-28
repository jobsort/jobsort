---
name: "Degree of an Array"
title: "LeetCode Degree of an Array Solution"
description: "Solution for given a non-empty array of non-negative integers nums, the degree of this array is defined as the maximum frequency of any one of its elements. Your task is to find the smallest possible length of a (contiguous) subarray of nums, that has the same degree as nums."
published: "2021-08-30 PDT"
modified: "2021-08-30 PDT"
---

# Degree of an Array Problem & Solution

Given a non-empty array of non-negative integers `nums`, the degree of this array is defined as the maximum frequency of any one of its elements.

Your task is to find the smallest possible length of a (contiguous) subarray of `nums`, that has the same degree as `nums`.

See the [degree of an array problem on LeetCode](https://leetcode.com/problems/degree-of-an-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int findShortestSubArray(vector<int>& nums) {
    int degree = 0;
    unordered_map<int, help> freq;
    for (int i = 0; i < nums.size(); ++i) {
      if (freq.find(nums[i]) == freq.end()) {
        freq[nums[i]] = {1, i, i};
      } else {
        ++freq[nums[i]].count;
        freq[nums[i]].high = i;
      }

      degree = max(degree, freq[nums[i]].count);
    }

    int argdegree = numeric_limits<int>::max();
    for (auto it = freq.begin(); it != freq.end(); ++it) {
      if (it->second.count == degree) {
        argdegree = min(argdegree, it->second.high - it->second.low + 1);
      }
    }

    return argdegree;
  }

private:
  struct help {
    int count;
    int low;
    int high;
  };
};
```
