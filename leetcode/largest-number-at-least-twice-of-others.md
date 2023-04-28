# Largest Number at Least Twice of Others Problem & Solution

You are given an integer array `nums` where the largest integer is unique.

Determine whether the largest element in the array is at least twice as much as every other number in the array.
If it is, return the index of the largest element, or return -1 otherwise.

See the [largest number at least twice of others problem on LeetCode](https://leetcode.com/problems/largest-number-at-least-twice-of-others).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int dominantIndex(vector<int>& nums) {
    int largest = numeric_limits<int>::min();
    int arglargest = -1;
    for (int i = 0; i < nums.size(); ++i) {
      if (largest < nums[i]) {
        largest = nums[i];
        arglargest = i;
      }
    }

    for (int i = 0; i < nums.size(); ++i) {
      if (nums[i] < largest &&
          nums[i] > largest / 2) {
        return -1;
      }
    }

    return arglargest;
  }
};
```
