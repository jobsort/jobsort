# License Key Formatting Problem & Solution

You are given a license key represented as a string `s` that consists of only alphanumeric characters and dashes.
The string is separated into n + 1 groups by n dashes.
You are also given an integer `k`.

We want to reformat the string `s` such that each group contains exactly `k` characters, except for the first group, which could be shorter than `k` but still must contain at least one character.
Furthermore, there must be a dash inserted between two groups, and you should convert all lowercase letters to uppercase.

Return the reformatted license key.

See the [license key formatting problem on LeetCode](https://leetcode.com/problems/license-key-formatting).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string licenseKeyFormatting(string s, int k) {
    int len = 0;
    for (int i = 0; i < s.size(); ++i) {
      len += s[i] != '-' ? 1 : 0;
    }

    // Takes care of the case when `s` is made up of only `-`.
    if (len == 0) {
      return "";
    }

    string result(len + len / k + (len % k == 0 ? -1 : 0), '-');
    int j = result.size() - 1;
    int jj = 0;
    for (int i = s.size() - 1; i >= 0; --i) {
      if (s[i] == '-') {
        continue;
      }

      // Keeps track of how many non `-` characters have been inserted.
      ++jj;

      result[j--] = toupper(s[i]);
      if (j > 0 && jj % k == 0) {
        --j;
      }
    }

    return result;
  }
};
```
