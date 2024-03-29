# Find the Difference Problem & Solution

You are given two strings `s` and `t`.
String `t` is generated by random shuffling string `s` and then add one more letter at a random position.
Return the letter that was added to `t`.

See the [find the difference problem on LeetCode](https://leetcode.com/problems/find-the-difference).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  char findTheDifference(string s, string t) {
    unordered_map<char, int> histogram;

    for (int i = 0; i < s.size(); ++i) {
      if (histogram.find(s[i]) == histogram.end()) {
        histogram[s[i]] = 1;
      } else {
        ++histogram[s[i]];
      }
    }

    for (int i = 0; i < t.size(); ++i) {
      if (histogram.find(t[i]) == histogram.end()) {
        return t[i];
      } else if (histogram[t[i]]-- == 0) {
        return t[i];
      }
    }

    return 0;
  }
};
```
