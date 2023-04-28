# Remove Letter to Equalize Frequency Problem & Solution

See the [remove letter to equalize frequency problem on LeetCode](https://leetcode.com/problems/remove-letter-to-equalize-frequency).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool equalFrequency(string word) {
    unordered_map<char, int> freq;
    for (char c : word) {
      ++freq[c];
    }

    int min = numeric_limits<int>::max(), argmin,
        max = numeric_limits<int>::min(), argmax;
    for (auto [k, v] : freq) {
      if (min > v) {
        min = v;
        argmin = k;
      }
      if (max < v) {
        max = v;
        argmax = k;
      }
    }

    // Tests if we have only unique characters.
    if (freq[argmax] == 1) {
      return true;
    }

    // Tests if we can remove the character that appears only once.
    if (freq[argmin] == 1) {
      bool ok = true;
      for (auto [k, v] : freq) {
        if (k != argmin && v != freq[argmax]) {
          ok = false;
          break;
        }
      }

      if (ok) { return ok; }
    }

    --freq[argmax];

    // Tests if the remaining characters after deducting one from the highest frequency are same.
    bool ok = true;
    for (auto [k, v] : freq) {
      if (v != freq[argmax]) {
        ok = false;
        break;
      }
    }

    return ok;
  }
};
```
