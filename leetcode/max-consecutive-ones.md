# Max Consecutive Ones Problem & Solution

Given a binary array `nums`, return the maximum number of consecutive 1's in the array.

See the [max consecutive ones problem on LeetCode](https://leetcode.com/problems/max-consecutive-ones).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int findMaxConsecutiveOnes(vector<int>& nums) {
    int result = 0;
    int count = 0;
    for (int i = 0; i <= nums.size(); ++i) {
      if (i < nums.size() && nums[i] == 1) {
        ++count;
      } else {
        result = max(result, count);
        count = 0;
      }
    }

    return result;
  }
};
```
