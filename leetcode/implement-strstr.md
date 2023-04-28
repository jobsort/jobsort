# Implement strstr Problem & Solution

Implement `strstr()`. Return the index of the first occurrence of `needle` in `haystack`, or -1 if `needle` is not part of `haystack`.

See the [implement strstr problem on LeetCode](https://leetcode.com/problems/implement-strstr).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int strStr(string haystack, string needle) {
    if (needle.empty()) {
      return 0;
    }

    for (int i = 0; i <= (int)(haystack.size() - needle.size()); ++i) {
      bool ok = true;
      for (int j = 0; j < needle.size(); ++j) {
        ok &= haystack[i + j] == needle[j];
        if (!ok) {
          break;
        }
      }

      if (ok) {
        return i;
      }
    }

    return -1;
  }
};
```
