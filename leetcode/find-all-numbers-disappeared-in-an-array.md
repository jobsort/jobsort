# Find All Numbers Disappeared in an Array Problem & Solution

Given an array `nums` of `n` integers where `nums[i]` is in the range `[1, n]`, return an array of all the integers in the range `[1, n]` that do not appear in `nums`.

See the [find all numbers disappeared in an array problem on LeetCode](https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> findDisappearedNumbers(vector<int>& nums) {
    vector<int> results;

    for (int i = 0; i < nums.size(); ++i) {
      int j = abs(nums[i]);
      if (nums[j - 1] > 0) {

        // Flips the sign for the positions of the numbers we iterated on.
        nums[j - 1] *= -1;
      }
    }

    for (int i = 0; i < nums.size(); ++i) {

      // The missing numbers will be the positions which are still positive integers.
      if (nums[i] > 0) {
        results.push_back(i + 1);
      }
    }

    return results;
  }
};
```
