# Buddy Strings Problem & Solution

See the [buddy strings problem on LeetCode](https://leetcode.com/problems/buddy-strings).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool buddyStrings(string s, string goal) {
    if (s.size() != goal.size()) { return false; }

    int different = 0;
    bool swappable = false;
    vector<int> freq('z' - 'a' + 1),
                freq1('z' - 'a' + 1),
                freq2('z' - 'a' + 1);
    for (int i = 0; i < s.size(); ++i) {
      if (s[i] != goal[i]) {
        ++different;
        ++freq1[s[i] - 'a'];
        ++freq2[goal[i] - 'a'];
      } else if (++freq[s[i] - 'a'] == 2) {
        swappable = true;
      }
    }

    if (different == 2) {
      for (int i = 0; i < freq1.size(); ++i) {
        if (freq1[i] != freq2[i]) {
          return false;
        }
      }

      return true;
    }

    return different == 0 && swappable;
  }
};
```
