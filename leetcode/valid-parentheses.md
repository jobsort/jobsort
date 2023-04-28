# Valid Parentheses Problem & Solution

Given a string `s` containing just the characters `(`, `)`, `{`, `}`, `[` and `]`, determine if the input string is valid.

See the [valid parentheses problem on LeetCode](https://leetcode.com/problems/valid-parentheses).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isValid(string s) {
    stack<char> sc;

    for (int i = 0; i < s.size(); ++i) {
      if (s[i] == '(' || s[i] == '[' || s[i] == '{') {
        sc.push(s[i]);
      } else if (!sc.empty() && ((s[i] == ')' && sc.top() == '(') ||
                                 (s[i] == ']' && sc.top() == '[') ||
                                 (s[i] == '}' && sc.top() == '{'))) {
        sc.pop();
      } else {
        return false;
      }
    }

    return sc.empty();
  }
};
```
