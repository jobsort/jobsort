# Add Digits Problem & Solution

Given an integer `num`, repeatedly add all its digits until the result has only one digit, and return it.

See the [add digits problem on LeetCode](https://leetcode.com/problems/add-digits).

## C++ Solution

The runtime complexity of this algorithm is $O(1)$.

```cpp
#pragma GCC optimize("Ofast")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int addDigits(int num) {
    if (num == 0) {
      return 0;
    }

    // https://en.wikipedia.org/wiki/Digital_root
    return 1 + (num - 1) % 9;
  }
};
```
