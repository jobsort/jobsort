# Left and Right Sum Differences Problem & Solution

See the [left and right sum differences problem on LeetCode](https://leetcode.com/problems/left-and-right-sum-differences).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> leftRigthDifference(vector<int>& nums) {
    vector<int> result(nums.size());

    int right = 0;
    for (int num : nums) {
      right += num;
    }

    int left = 0;
    for (int i = 0; i < nums.size(); ++i) {
      right -= nums[i];
      result[i] = abs(left - right);
      left += nums[i];
    }

    return result;
  }
};
```
