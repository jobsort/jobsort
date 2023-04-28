# Maximum Subarray Problem & Solution

Given an integer array `nums`, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

See the [maximum subarray problem on LeetCode](https://leetcode.com/problems/maximum-subarray).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int maxSubArray(vector<int>& nums) {
    int largest = INT_MIN;
    int sum = 0;

    for (int i = 0; i < nums.size(); ++i) {

      // Breaks the streak of contiguous subarray if the current number is
      // greater than the running sum; but, only if the sum is negative.
      if (nums[i] >= sum && sum < 0) {
        sum = nums[i];
      } else {
        sum += nums[i];
      }

      largest = max(largest, sum);
    }

    return largest;
  }
};
```
