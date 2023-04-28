# Permutations Problem & Solution

See the [permutations problem on LeetCode](https://leetcode.com/problems/permutations).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("max-inline-insns-recursive-auto")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> permute(vector<int>& nums) {
    vector<vector<int>> results;
    
    permute(0, nums, results);
    
    return results;
  }
  
private:
  void permute(int pivot, vector<int>& nums, vector<vector<int>>& results) {
    if (pivot == nums.size()) {
      results.push_back(nums);
      return;
    }
    
    for (int i = pivot; i < nums.size(); ++i) {
      swap(nums[i], nums[pivot]);
      permute(pivot + 1, nums, results);
      swap(nums[i], nums[pivot]);
    }
  }
};
```
