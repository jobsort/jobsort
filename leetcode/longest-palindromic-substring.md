# Longest Palindromic Substring Problem & Solution

See the [longest palindromic substring problem on LeetCode](https://leetcode.com/problems/longest-palindromic-substring).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string longestPalindrome(string s) {
    string best;
    bool dp[s.size()][s.size()];
    memset(dp, false, sizeof(dp));

    for (int i = 0; i < s.size(); ++i) {
      dp[i][i] = true;

      if (i < s.size() - 1) {
        dp[i][i + 1] = s[i] == s[i + 1];
      }
    }

    // `j` represents the length offset of the palindrome.
    for (int j = 2; j < s.size(); ++j) {
      for (int i = 0; i < s.size() - j; ++i) {
        dp[i][i + j] = s[i] == s[i + j] && dp[i + 1][i + j - 1];
      }
    }

    for (int i = 0; i < s.size(); ++i) {
      for (int j = 0; j < s.size(); ++j) {
        if (dp[i][j] && best.size() < j - i + 1) {
          best = s.substr(i, j - i + 1);
        }
      }
    }

    return best;
  }
};
```
