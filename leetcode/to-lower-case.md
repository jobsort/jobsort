# To Lower Case Problem & Solution

Given a string `s`, return the string after replacing every uppercase letter with the same lowercase letter.

See the [to lower case problem on LeetCode](https://leetcode.com/problems/to-lower-case).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string toLowerCase(string s) {
    for (int i = 0; i < s.size(); ++i) {
      if (s[i] >= 'A' && s[i] <= 'Z') {
        s[i] = s[i] - 'A' + 'a';
      }
    }

    return s;
  }
};
```
