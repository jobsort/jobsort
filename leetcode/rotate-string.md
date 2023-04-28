# Rotate String Problem & Solution

Given two strings `s` and `goal`, return true if and only if `s` can become `goal` after some number of shifts on `s`.

A shift on `s` consists of moving the leftmost character of `s` to the rightmost position.

For example, if `s = "abcde"`, then it will be `"bcdea"` after one shift.

See the [rotate string problem on LeetCode](https://leetcode.com/problems/rotate-string).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool rotateString(string s, string goal) {
    for (int i = 0; i < s.size(); ++i) {
      if (s == goal) {
        return true;
      }

      s = s.substr(1) + s.substr(0, 1);
    }

    return false;
  }
};
```
