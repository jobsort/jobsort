# 4Sum Problem & Solution

See the [4sum problem on LeetCode](https://leetcode.com/problems/4sum).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

using namespace std;

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> fourSum(vector<int>& nums, int target) {
    vector<vector<int>> result;

    sort(nums.begin(), nums.end());
    
    for (int i = 0; i < (int)nums.size() - 3; ++i) {
      for (int j = i + 1; j < (int)nums.size() - 2; ++j) {
        int k = j + 1;
        int l = nums.size() - 1;
        while (k < l) {
          long sum = static_cast<long>(nums[i]) + nums[j] + nums[k] + nums[l];
          if (sum < target) {
            ++k;
          } else if (sum > target) {
            --l;
          } else {
            result.push_back({nums[i], nums[j], nums[k], nums[l]});
            while (k < nums.size() - 1 && nums[k] == nums[k + 1]) { ++k; }
            while (l > 0 && nums[l] == nums[l - 1]) { --l; }
            ++k;
            --l;
          }
        }
        
        while (j < nums.size() - 1 && nums[j] == nums[j + 1]) { ++j; }
      }
      
      while (i < nums.size() - 1 && nums[i] == nums[i + 1]) { ++i; }
    }
    
    return result;
  }
};
```
