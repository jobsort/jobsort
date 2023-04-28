# Difference between Element Sum and Digit Sum of an Array Problem & Solution

See the [difference between element sum and digit sum of an array problem on LeetCode](https://leetcode.com/problems/difference-between-element-sum-and-digit-sum-of-an-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC ivdep

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int differenceOfSum(vector<int>& nums) {
    int esum = 0, dsum = 0;
    for (int num : nums) {
      esum += num;

      while (num > 0) {
        dsum += num % 10;
        num /= 10;
      }
    }

    return abs(esum - dsum);
  }
};
```
