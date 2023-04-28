# Minimum Subsequence in Non-Increasing Order Problem & Solution

See the [minimum subsequence in non-increasing order problem on LeetCode](https://leetcode.com/problems/minimum-subsequence-in-non-increasing-order).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> minSubsequence(vector<int>& nums) {
    sort(nums.begin(), nums.end(), greater<int>());
    
    int total = 0;
    for (int i = 0; i < nums.size(); ++i) {
      total += nums[i];
    }

    int i = 0, sum = 0;
    vector<int> results;
    while (sum <= total) {
      results.push_back(nums[i]);

      sum += nums[i];
      total -= nums[i];

      ++i;
    }

    return results;
  }
};
```
