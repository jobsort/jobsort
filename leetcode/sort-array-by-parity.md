# Sort Array by Parity Problem & Solution

Given an integer array `nums`, move all the even integers at the beginning of the array followed by all the odd integers.

Return any array that satisfies this condition.

See the [sort array by parity problem on LeetCode](https://leetcode.com/problems/sort-array-by-parity).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> sortArrayByParity(vector<int>& nums) {
    int low = 0;
    int high = nums.size() - 1;
    while (low < high) {
      if (nums[low] % 2 != 0) {
        swap(nums[low], nums[high--]);
      } else {
        ++low;
      }
    }

    return nums;
  }
};
```
