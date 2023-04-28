# First Letter to Appear Twice Problem & Solution

See the [first letter to appear twice problem on LeetCode](https://leetcode.com/problems/first-letter-to-appear-twice).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  char repeatedCharacter(string s) {
    vector<char> freq('z' - 'a' + 1);
    for (auto c : s) {
      if (++freq[c - 'a'] == 2) {
        return c;
      }
    }

    assert(false); // unreachable
    return ' ';
  }
};
```
