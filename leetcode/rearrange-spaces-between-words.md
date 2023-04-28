# Rearrange Spaces Between Words Problem & Solution

See the [rearrange spaces between words problem on LeetCode](https://leetcode.com/problems/rearrange-spaces-between-words).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string reorderSpaces(string text) {
    int spaces = 0, words = 0;
    for (int i = 0; i < text.size(); ++i) {
      if (text[i] == ' ') { ++spaces; }

      if ((i == 0 || text[i - 1] == ' ') && text[i] != ' ') {
        ++words;
      }
    }

    int width = words > 1 ? spaces / (words - 1) : 0;
    string result(text.size(), ' ');
    int i = 0, j = 0;

    while (j < text.size()) {
      while (j < text.size() && text[j] == ' ') {
        ++j;
      }

      while (j < text.size() && text[j] != ' ') {
        result[i] = text[j];

        ++i;
        ++j;
      }
      
      i += width;
    }

    return result;
  }
};
```
