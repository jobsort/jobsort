# Reverse Integer Problem & Solution

Given a signed 32-bit integer `x`, return `x` with its digits reversed. If reversing `x` causes the value to go outside the signed 32-bit integer range, then return 0.

See the [reverse integer problem on LeetCode](https://leetcode.com/problems/reverse-integer).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int reverse(int x) {
    if (x == INT_MIN) {
      return 0;
    }

    // abs(INT_MIN) == INT_MIN because of overflow, thus considering the edge case above.
    int y = 0;
    int tmp = abs(x);
    while (tmp != 0) {

      // Tests for overflow at each step.
      // If you're going to do `y * 10` and it may overflow, then you need to test for `y > INT_MAX / 10`.
      if (y > INT_MAX / 10 || y * 10 > INT_MAX - tmp % 10) {
        return 0;
      }

      y = y * 10 + tmp % 10;
      tmp /= 10;
    }

    if (x < 0) {
      y *= -1;
    }

    return y;
  }
};
```
