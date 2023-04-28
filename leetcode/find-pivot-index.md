# Find Pivot Index Problem & Solution

Given an array of integers `nums`, calculate the pivot index of this array.

The pivot index is the index where the sum of all the numbers strictly to the left of the index is equal to the sum of all the numbers strictly to the index's right.

If the index is on the left edge of the array, then the left sum is 0 because there are no elements to the left. This also applies to the right edge of the array.

Return the leftmost pivot index. If no such index exists, return -1.

See the [find pivot index problem on LeetCode](https://leetcode.com/problems/find-pivot-index).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int pivotIndex(vector<int>& nums) {

    // Memoizes the sums from left to right.
    vector<int> leftSum(nums.size(), 0);
    for (int i = 1; i < nums.size(); ++i) {
      leftSum[i] = leftSum[i - 1] + nums[i - 1];
    }

    // Memoizes the sums from right to left.
    vector<int> rightSum(nums.size(), 0);
    for (int i = nums.size() - 2; i >= 0; --i) {
      rightSum[i] = rightSum[i + 1] + nums[i + 1];
    }

    for (int i = 0; i < nums.size(); ++i) {
      if (leftSum[i] == rightSum[i]) {
        return i;
      }
    }

    return -1;
  }
};
```
