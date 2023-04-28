# Roman to Integer Problem & Solution

Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.
Given a roman numeral, convert it to an integer.

See the [roman to integer problem on LeetCode](https://leetcode.com/problems/roman-to-integer).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int romanToInt(string s) {
    map<char, int> numerals = {
      {'I',    1},
      {'V',    5},
      {'X',   10},
      {'L',   50},
      {'C',  100},
      {'D',  500},
      {'M', 1000},
    };

    int sum = 0;
    int i = 0;
    while (i < s.size()) {
      if (i + 1 < s.size() && ((s[i] == 'I' && (s[i + 1] == 'V' || s[i + 1] == 'X')) ||
                               (s[i] == 'X' && (s[i + 1] == 'L' || s[i + 1] == 'C')) ||
                               (s[i] == 'C' && (s[i + 1] == 'D' || s[i + 1] == 'M')))) {
        sum += numerals[s[i + 1]] - numerals[s[i]];
        i += 2;
      } else {
        sum += numerals[s[i]];
        ++i;
      }
    }

    return sum;
  }
};
```
