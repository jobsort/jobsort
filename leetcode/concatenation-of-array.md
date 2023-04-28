# Concatenation of Array Problem & Solution

See the [concatenation of array problem on LeetCode](https://leetcode.com/problems/concatenation-of-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> getConcatenation(vector<int>& nums) {
    nums.insert(nums.end(), nums.begin(), nums.end());

    return nums;
  }
};
```
