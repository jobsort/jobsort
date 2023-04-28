# Reverse Words in a String III Problem & Solution

Given a string `s`, reverse the order of characters in each word within a sentence while still preserving whitespace and initial word order.

See the [reverse words in a string iii problem on LeetCode](https://leetcode.com/problems/reverse-words-in-a-string-iii).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string reverseWords(string s) {
    int i = 0;
    while (i < s.size()) {
      while (s[i] == ' ') { ++i; }

      int j = i + 1;
      while (j < s.size() && s[j] != ' ') { ++j; }

      reverse(s.begin() + i, s.begin() + j);

      i = j + 1;
    }

    return s;
  }
};
```
