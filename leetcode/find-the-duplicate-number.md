# Find the Duplicate Number Problem & Solution

See the [find the duplicate number problem on LeetCode](https://leetcode.com/problems/find-the-duplicate-number).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int findDuplicate(vector<int>& nums) {
    int result;

    int low = 1, high = nums.size() - 1;
    while (low <= high) {
      int mid = low + (high - low) / 2;

      int count = 0;
      for (auto a : nums) {
        if (a <= mid) {
          ++count;
        }
      }

      if (count <= mid) {
        low = mid + 1;
      } else {
        high = mid - 1;
      }
    }

    return high + 1;
  }
};
```
