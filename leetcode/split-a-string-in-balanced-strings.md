# Split a String in Balanced Strings Problem & Solution

See the [split a string in balanced strings problem on LeetCode](https://leetcode.com/problems/split-a-string-in-balanced-strings).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int balancedStringSplit(string s) {
    int balance = 0, result = 0;
    for (char c : s) {
      balance += c == 'L' ? +1 : -1;
      if (balance == 0) {
        ++result;
      }
    }

    return result;
  }
};
```
