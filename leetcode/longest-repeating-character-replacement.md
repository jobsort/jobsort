# Longest Repeating Character Replacement Problem & Solution

See the [longest repeating character replacement problem on LeetCode](https://leetcode.com/problems/longest-repeating-character-replacement).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int characterReplacement(string s, int k) {
    int low = 0, high = s.size();
    while (low <= high) {
      int mid = low + (high - low) / 2;
      bool ok = false;

      vector<int> freq('Z' - 'A' + 1);

      for (int i = 0; i < s.size(); ++i) {
        ++freq[s[i] - 'A'];

        if (i >= mid) {
          --freq[s[i - mid] - 'A'];
        }

        if (i >= mid - 1) {
          int max = freq[0];
          for (int i = 1; i < freq.size(); ++i) {
            if (freq[i] > max) {
              max = freq[i];
            }
          }

          if (k >= mid - max) {
            ok = true;
            break;
          }
        }
      }

      if (ok) {
        low = mid + 1;
      } else {
        high = mid - 1;
      }
    }

    return high;
  }
};
```
