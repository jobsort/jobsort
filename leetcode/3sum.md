---
name: "3Sum"
title: "LeetCode 3Sum Solution"
description: "Solution for the 3sum problem from LeetCode."
published: "2022-04-03 PDT"
modified: "2022-04-03 PDT"
---

# 3Sum Problem & Solution

See the [3sum problem on LeetCode](https://leetcode.com/problems/3sum).

## C++ Solution

The runtime complexity of this algorithm is $O(n\log{}n + n^2)$.

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> threeSum(vector<int>& nums) {
    vector<vector<int>> result;

    sort(nums.begin(), nums.end());

    for (int i = 0; i < (int)nums.size() - 2; ++i) {
      int j = i + 1;
      int k = nums.size() - 1;
      while (j < k) {
        int sum = nums[i] + nums[j] + nums[k];
        if (sum > 0) {
          —k;
        } else if (sum < 0) {
          ++j;
        } else {
          result.push_back({nums[i], nums[j], nums[k]});
          while (j < (int)nums.size() - 1 && nums[j] == nums[j + 1]) ++j;
          while (k > 0 && nums[k] == nums[k - 1]) —k;
          ++j;
          —k;
        }
      }

      while (i < (int)nums.size() - 1 && nums[i] == nums[i + 1]) ++i;
    }

    return vector<vector<int>>(result.begin(), result.end());
  }
};
```
