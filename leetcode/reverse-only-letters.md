# Reverse Only Letters Problem & Solution

Given a string `s`, reverse the string according to the following rules:

- All the characters that are not English letters remain in the same position.
- All the English letters (lowercase or uppercase) should be reversed.

Return `s` after reversing it.

See the [reverse only letters problem on LeetCode](https://leetcode.com/problems/reverse-only-letters).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string reverseOnlyLetters(string s) {
    int low = 0;
    int high = s.size() - 1;

    while (low < high) {
      char llow = tolower(s[low]);
      if (llow < 'a' || llow > 'z') {
        ++low;
        continue;
      }

      char lhigh = tolower(s[high]);
      if (lhigh < 'a' || lhigh > 'z') {
        --high;
        continue;
      }

      swap(s[low], s[high]);
      ++low;
      --high;
    }

    return s;
  }
};
```
