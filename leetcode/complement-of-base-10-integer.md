# Complement of Base 10 Integer Problem & Solution

The complement of an integer is the integer you get when you flip all the `0`'s to `1`'s and all the `1`'s to `0`'s in its binary representation.

For example, the integer `5` is `"101"` in binary and its complement is `"010"` which is the integer `2`.
Given an integer `n`, return its complement.

See the [complement of base 10 integer problem on LeetCode](https://leetcode.com/problems/complement-of-base-10-integer).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int bitwiseComplement(int n) {
    if (n == 0) {
      return 1;
    }

    vector<int> bits;
    while (n > 0) {
      bits.push_back(n % 2);
      n /= 2;
    }

    int m = 0;
    for (int i = bits.size() - 1; i >= 0; --i) {
      m *= 2;
      m += bits[i] == 0 ? 1 : 0;
    }

    return m;
  }
};
```
