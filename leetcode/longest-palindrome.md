# Longest Palindrome Problem & Solution

Given a string `s` which consists of lowercase or uppercase letters, return the length of the longest palindrome that can be built with those letters.

Letters are case sensitive, for example, "Aa" is not considered a palindrome here.

See the [longest palindrome problem on LeetCode](https://leetcode.com/problems/longest-palindrome).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int longestPalindrome(string s) {
    unordered_map<char, int> map;

    for (int i = 0; i < s.size(); ++i) {
      ++map[s[i]];
    }

    int even = 0;
    int odd = 0;
    for (auto& it: map) {
      if (it.second % 2 == 0) {
        even += it.second;
      } else {
        even += it.second - 1;
        odd = 1;
      }
    }

    return even + odd;
  }
};
```
