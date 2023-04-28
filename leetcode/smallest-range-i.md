# Smallest Range I Problem & Solution

You are given an integer array `nums` and an integer `k`.

In one operation, you can choose any index `i` where `0 <= i < nums.length` and change `nums[i]` to `nums[i] + x` where `x` is an integer from the range `[-k, k]`. You can apply this operation at most once for each index `i`.

The score of `nums` is the difference between the maximum and minimum elements in `nums`.

Return the minimum score of `nums` after applying the mentioned operation at most once for each index in it.

See the [smallest range i problem on LeetCode](https://leetcode.com/problems/smallest-range-i).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int smallestRangeI(vector<int>& nums, int k) {
    int low = numeric_limits<int>::max();
    int high = numeric_limits<int>::min();
    for (int i = 0; i < nums.size(); ++i) {
      low = min(low, nums[i]);
      high = max(high, nums[i]);
    }

    low += k;
    high -= k;

    // Tests if we can change all nums to be the same.
    if (low > high) {
      return 0;
    }

    return high - low;
  }
};
```
