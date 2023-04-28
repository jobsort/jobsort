# Alternating Digit Sum Problem & Solution

See the [alternating digit sum problem on LeetCode](https://leetcode.com/problems/alternating-digit-sum).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int alternateDigitSum(int n) {

    // `floor(log10(n) + 1)` counts the number of digits in base 10.
    int sign = (int)floor(log10(n) + 1) % 2 ? 1 : -1;
    int sum = 0;
    while (n > 0) {
      sum += sign * (n % 10);
      n /= 10;
      sign *= -1;
    }

    return sum;
  }
};
```
