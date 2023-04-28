# Ransom Note Problem & Solution

Given two strings `ransomNote` and `magazine`, return true if `ransomNote` can be constructed from `magazine` and false otherwise.
Each letter in `magazine` can only be used once in `ransomNote`.

See the [ransom note problem on LeetCode](https://leetcode.com/problems/ransom-note).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool canConstruct(string ransomNote, string magazine) {
    unordered_map<char, int> histogram;
    for (int i = 0; i < magazine.size(); ++i) {
      if (histogram.find(magazine[i]) != histogram.end()) {
        ++histogram[magazine[i]];
      } else {
        histogram[magazine[i]] = 1;
      }
    }

    for (int i = 0; i < ransomNote.size(); ++i) {
      if (histogram.find(ransomNote[i]) == histogram.end()) {
        return false;
      } else {
        --histogram[ransomNote[i]];
      }
    }

    for (unordered_map<char, int>::iterator it = histogram.begin(); it != histogram.end(); ++it) {
      if (it->second < 0) {
        return false;
      }
    }

    return true;
  }
};
```
