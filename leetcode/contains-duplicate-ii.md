# Contains Duplicate II Problem & Solution

Given an integer array `nums` and an integer `k`, return true if there are two distinct indices `i` and `j` in the array such that `nums[i] == nums[j]` and `abs(i - j) <= k`.

See the [contains duplicate ii problem on LeetCode](https://leetcode.com/problems/contains-duplicate-ii).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool containsNearbyDuplicate(vector<int>& nums, int k) {

    // Represents the most recent position we saw for each number.
    unordered_map<int, int> js;
    for (int i = 0; i < nums.size(); ++i) {
      if (js.find(nums[i]) != js.end() &&
          abs(i - js[nums[i]]) <= k) {
        return true;
      }

      // Keeps track of the last position we saw for `nums[i]`.
      js[nums[i]] = i;
    }

    return false;
  }
};
```
