# 3Sum Closest Problem & Solution

See the [3sum closest problem on LeetCode](https://leetcode.com/problems/3sum-closest).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int threeSumClosest(vector<int>& nums, int target) {
    sort(nums.begin(), nums.end());

    auto best = target;
    auto min = numeric_limits<int>::max();

    for (auto i = 0; i < (int)nums.size() - 2; ++i) {
      auto j = i + 1;
      auto k = nums.size() - 1;
      while (j < k) {
        auto sum = nums[i] + nums[j] + nums[k];

        if (abs(target - sum) < min) {
          min = abs(target - sum);
          best = sum;
        }
        
        if (sum > target) {
          --k;
        } else if (sum < target) {
          ++j;
        } else {
          break;
        }
      }
    }
    
    return best;
  }
};
```
