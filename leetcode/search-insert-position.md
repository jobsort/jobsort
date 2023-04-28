# Search Insert Position Problem & Solution

Given a sorted array of distinct integers and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

See the [search insert position problem on LeetCode](https://leetcode.com/problems/search-insert-position).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int searchInsert(vector<int>& nums, int target) {
    int low = 0;
    int mid = 0;
    int high = nums.size();

    while (low < high) {
      mid = low + (high - low) / 2;
      if (nums[mid] == target) {
        return mid;
      } else if (nums[mid] > target) {
        high = mid;
      } else {
        low = mid + 1;
      }
    }

    return low;
  }
};
```
