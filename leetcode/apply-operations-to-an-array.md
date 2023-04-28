# Apply Operations to an Array Problem & Solution

See the [apply operations to an array problem on LeetCode](https://leetcode.com/problems/apply-operations-to-an-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> applyOperations(vector<int>& nums) {
    for (int i = 0; i < nums.size() - 1; ++i) {
      if (nums[i] == nums[i + 1]) {
        nums[i] *= 2;
        nums[i + 1] = 0;
      }
    }

    // Moves all zeroes at the end of `nums`.
    stable_partition(nums.begin(), nums.end(), [](int n){ return n != 0; });

    return nums;
  }
};
```
