# Reverse Vowels of a String Problem & Solution

Given a string `s`, reverse only all the vowels in the string and return it.
The vowels are 'a', 'e', 'i', 'o', and 'u', and they can appear in both cases.

See the [reverse vowels of a string problem on LeetCode](https://leetcode.com/problems/reverse-vowels-of-a-string).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string reverseVowels(string s) {
    unordered_map<char, bool> vowels{
      { 'a', true }, { 'A', true },
      { 'e', true }, { 'E', true },
      { 'i', true }, { 'I', true },
      { 'o', true }, { 'O', true },
      { 'u', true }, { 'U', true },
    };

    int low = 0;
    int high = s.size() - 1;
    while (low < high) {
      while (low < high && vowels.find(s[low]) == vowels.end()) {
        ++low;
      }
      while (low < high && vowels.find(s[high]) == vowels.end()) {
        --high;
      }

      swap(s[low++], s[high--]);
    }

    return s;
  }
};
```
