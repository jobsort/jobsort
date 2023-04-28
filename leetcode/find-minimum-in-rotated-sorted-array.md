# Find Minimum in Rotated Sorted Array Problem & Solution

See the [find minimum in rotated sorted array problem on LeetCode](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int findMin(vector<int>& nums) {
    if (nums.front() < nums.back()) {
      return nums.front();
    }

    int low = 0, high = nums.size() - 1;
    while (low < high) {
      int mid = low + (high - low) / 2;

      if (mid > 0 && nums[mid - 1] > nums[mid]) {
        return nums[mid];
      }

      if (nums[mid] > nums[mid + 1]) {
        return nums[mid + 1];
      }

      if (nums.front() < nums[mid]) {
        low = mid + 1;
      } else {
        high = mid - 1;
      }
    }

    return nums[0];
  }
};
```
