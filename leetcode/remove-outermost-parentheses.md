# Remove Outermost Parentheses Problem & Solution

See the [remove outermost parentheses problem on LeetCode](https://leetcode.com/problems/remove-outermost-parentheses).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string removeOuterParentheses(string s) {
    string t;
    int start = 0;
    int count = 0;
    for (int i = 0; i < s.size(); ++i) {
      if (s[i] == '(') {
        ++count;
      } else {
        --count;
      }

      if (count == 0) {
        t += s.substr(start + 1, i - start - 1);
        start = i + 1;
      }
    }

    return t;
  }
};
```
