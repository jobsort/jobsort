# Search in Rotated Sorted Array Problem & Solution

See the [search in rotated sorted array problem on LeetCode](https://leetcode.com/problems/search-in-rotated-sorted-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma");

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int search(vector<int>& nums, int target) {
    int low = 0, high = nums.size() - 1;

    while (high > low - 1) {
      int mid = low + (high - low) / 2;

      if (target == nums[mid]) {
        return mid;
      } else if (target > nums[mid]) {
        // should go right
        if (target <= nums[high] || nums[low] < nums[mid]) {
          low = mid + 1;
        } else {
          high = mid - 1;
        }
      } else {
        // should go left
        if (target >= nums[low] || nums[mid] < nums[high]) {
          high = mid - 1;
        } else {
          low = mid + 1;
        }
      }
    }

    return -1;
  }
};
```
