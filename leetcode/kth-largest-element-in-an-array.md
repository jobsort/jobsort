# Kth Largest Element in an Array Problem & Solution

See the [kth largest element in an array problem on LeetCode](https://leetcode.com/problems/kth-largest-element-in-an-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int findKthLargest(vector<int>& nums, int k) {
    int low = 0, high = nums.size() - 1;
    while (low < high) {
      int pivot = nums[high];
      auto it = partition(nums.begin() + low, nums.begin() + high + 1,
        [pivot](auto& a){ return a < pivot; });

      int dist = distance(nums.begin(), it);
      swap(nums[dist], nums[high]);

      if (k == nums.size() - dist) {
        break;
      } else if (k < nums.size() - dist) {
        low = dist + 1;
      } else {
        high = dist - 1;
      }
    }

    return nums[nums.size() - k];
  }
};
```
