# Check if Array is Sorted and Rotated Problem & Solution

See the [check if array is sorted and rotated problem on LeetCode](https://leetcode.com/problems/check-if-array-is-sorted-and-rotated).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool check(vector<int>& nums) {
    int rotations = 0;
    for (int i = 0; i < nums.size() - 1; ++i) {
      if (nums[i] > nums[i + 1]) {
        ++rotations;

        if (rotations > 1) {
          return false;
        }
      }
    }

    if (nums[nums.size() - 1] > nums[0]) {
      ++rotations;
    }
    
    return rotations <= 1;;
  }
};
```
