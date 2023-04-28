---
name: "Summary Ranges"
title: "LeetCode Summary Ranges Solution"
description: 'Solution for you are given a sorted unique integer array nums. Return the smallest sorted list of ranges that cover all the numbers in the array exactly. That is, each element of nums is covered by exactly one of the ranges, and there is no integer x such that x is in one of the ranges but not in nums. Each range [a,b] in the list should be output as: "a->b" if a != b "a" if a == b'
published: "2021-08-26 PDT"
modified: "2021-08-26 PDT"
---

# Summary Ranges Problem & Solution

You are given a sorted unique integer array `nums`.

Return the smallest sorted list of ranges that cover all the numbers in the array exactly.
That is, each element of `nums` is covered by exactly one of the ranges, and there is no integer `x` such that `x` is in one of the ranges but not in `nums`.

Each range `[a,b]` in the list should be output as:

- `"a->b"` if `a != b`
- `"a"` if `a == b`

See the [summary ranges problem on LeetCode](https://leetcode.com/problems/summary-ranges).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<string> summaryRanges(vector<int>& nums) {
    vector<string> results;
    int low = 0;
    for (int i = 0; i < nums.size(); ++i) {
      if ((i < nums.size() - 1 && nums[i] != nums[i + 1] - 1) ||
          (i == nums.size() - 1)) {
        if (low == i) {
          results.push_back(to_string(nums[low]));
        } else {
          results.push_back(to_string(nums[low]) + "->" + to_string(nums[i]));
        }

        low = i + 1;
      }
    }

    return results;
  }
};
```
