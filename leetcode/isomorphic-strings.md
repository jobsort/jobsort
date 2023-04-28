# Isomorphic Strings Problem & Solution

Given two strings `s` and `t`, determine if they are isomorphic.
Two strings `s` and `t` are isomorphic if the characters in `s` can be replaced to get `t`.
All occurrences of a character must be replaced with another character while preserving the order of characters.
No two characters may map to the same character, but a character may map to itself.

See the [isomorphic strings problem on LeetCode](https://leetcode.com/problems/isomorphic-strings).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isIsomorphic(string s, string t) {
    unordered_map<char, char> map;
    set<char> used;

    for (int i = 0; i < s.size(); ++i) {
      if (map.find(s[i]) == map.end() &&
          used.find(t[i]) == used.end()) {
        map[s[i]] = t[i];
        used.insert(t[i]);
      }

      if (map[s[i]] != t[i]) {
        return false;
      }
    }

    return true;
  }
};
```
