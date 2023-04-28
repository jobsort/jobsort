# Subsets Problem & Solution

See the [subsets problem on LeetCode](https://leetcode.com/problems/subsets).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("max-inline-insns-recursive-auto")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> subsets(vector<int>& nums) {
    vector<vector<int>> results;
    vector<int> result;

    subsets(nums, 0, result, results);

    return results;
  }

private:
  void subsets(vector<int>& nums, int i, vector<int>& result, vector<vector<int>>& results) {
    if (i == nums.size()) {
      results.push_back(result);
      return;
    }

    subsets(nums, i + 1, result, results);

    result.push_back(nums[i]);
    subsets(nums, i + 1, result, results);
    result.pop_back();
  }
};
```
