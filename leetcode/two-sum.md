# Two Sum Problem & Solution

Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.

See the [two sum problem on LeetCode](https://leetcode.com/problems/two-sum).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> twoSum(vector<int>& nums, int target) {
    for (int i = 0; i < nums.size() - 1; ++i) {
      for (int j = i + 1; j < nums.size(); ++j) {
        if (nums[i] + nums[j] == target) {
          return {i, j};
        }
      }
    }

    return {0, 1};
  }
};
```
