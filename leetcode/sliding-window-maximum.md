---
name: "Sliding Window Maximum"
title: "LeetCode Sliding Window Maximum Solution"
description: "Solution for the sliding window maximum problem from LeetCode."
published: "2022-12-24 PDT"
modified: "2022-12-24 PDT"
---

# Sliding Window Maximum Problem & Solution

See the [sliding window maximum problem on LeetCode](https://leetcode.com/problems/sliding-window-maximum).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> maxSlidingWindow(vector<int>& nums, int k) {
    vector<int> results;
    multiset<int> window;
    for (int i = 0; i < nums.size(); ++i) {
      if (i >= k) {
        window.erase(window.find(nums[i - k]));
      }

      window.insert(nums[i]);

      if (i >= k - 1) {
        results.push_back(*window.rbegin());
      }
    }

    return results;
  }
};
```
