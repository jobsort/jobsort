---
name: "Subsets II"
title: "LeetCode Subsets II Solution"
description: "Solution for the subsets ii problem from LeetCode."
published: "2023-01-12 PDT"
modified: "2023-01-12 PDT"
---

# Subsets II Problem & Solution

See the [subsets ii problem on LeetCode](https://leetcode.com/problems/subsets-ii).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("max-inline-insns-recursive,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> subsetsWithDup(vector<int>& nums) {
    vector<vector<int>> results;
    vector<int> result;

    sort(nums.begin(), nums.end());
    subsetsWithDup(nums, 0, result, results);

    return results;
  }

private:
  void subsetsWithDup(vector<int>& nums, int i, vector<int>& result, vector<vector<int>>& results) {
    results.push_back(result);

    if (i == nums.size()) { return; }

    for (int j = i; j < nums.size(); ++j) {
      result.push_back(nums[j]);
      subsetsWithDup(nums, j + 1, result, results);

      // Skips duplicate consecutive values.
      while (j < nums.size() - 1 && nums[j] == nums[j + 1]) {
        ++j;
      }

      result.pop_back();
    }
  }
};
```
