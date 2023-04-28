# Find All Anagrams in a String Problem & Solution

See the [find all anagrams in a string problem on LeetCode](https://leetcode.com/problems/find-all-anagrams-in-a-string).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> findAnagrams(string s, string p) {
    vector<int> results;

    vector<int> freq_s('z' - 'a' + 1),
                freq_p('z' - 'a' + 1);
    for (int i = 0; i < p.size(); ++i) {
      ++freq_p[p[i] - 'a'];
    }

    for (int i = 0; i < s.size(); ++i) {
      ++freq_s[s[i] - 'a'];

      if (i >= p.size()) {
        --freq_s[s[i - p.size()] - 'a'];
      }

      int j;
      for (j = 0; j < 'z' - 'a' + 1; ++j) {
        if (freq_s[j] != freq_p[j]) {
          break;
        }
      }

      if (j == 'z' - 'a' + 1) {
        results.push_back(i - p.size() + 1);
      }
    }

    return results;
  }
};
```
