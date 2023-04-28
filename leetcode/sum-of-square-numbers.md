# Sum of Square Numbers Problem & Solution

Given a non-negative integer `c`, decide whether there're two integers `a` and `b` such that `a^2 + b^2 = c`.

See the [sum of square numbers problem on LeetCode](https://leetcode.com/problems/sum-of-square-numbers).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool judgeSquareSum(int c) {
    for (int a = 0; a <= sqrt(c); ++a) {
      double b = sqrt(c - a * a);
      if (b == (int)b) {
        return true;
      }
    }

    return false;
  }
};
```
