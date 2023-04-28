# Length of Last Word Problem & Solution

Given a string `s`, which consists of some words separated by spaces, return the length of the last word in the string. If the last word does not exist, return 0.

See the [length of last word problem on LeetCode](https://leetcode.com/problems/length-of-last-word).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int lengthOfLastWord(string s) {
    int i = s.size() - 1;
    while (i >= 0 && s[i] == ' ') {
      --i;
    }

    int j = i;
    while (j >= 0 && s[j] != ' ') {
      --j;
    }

    return i - j;
  }
};
```
