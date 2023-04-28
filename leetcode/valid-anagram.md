# Valid Anagram Problem & Solution

Given two strings `s` and `t`, return true if `t` is an anagram of `s`, and false otherwise.

See the [valid anagram problem on LeetCode](https://leetcode.com/problems/valid-anagram).

## C++ Solution

The runtime complexity of this algorithm is $O(n + m)$.

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isAnagram(string s, string t) {
    unordered_map<char, int> histogram;

    for (int i = 0; i < s.size(); ++i) {
      if (histogram.find(s[i]) == histogram.end()) {
        histogram[s[i]] = 1;
      } else {
        ++histogram[s[i]];
      }
    }

    int count = histogram.size();
    for (int i = 0; i < t.size(); ++i) {
      if (histogram.find(t[i]) == histogram.end() ||
          histogram[t[i]] == 0) {
        return false;
      } else if (--histogram[t[i]] == 0) {
        --count;
      }
    }

    return count == 0;
  }
};
```
