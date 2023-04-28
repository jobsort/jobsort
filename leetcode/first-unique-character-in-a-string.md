# First Unique Character in a String Problem & Solution

Given a string `s`, find the first non-repeating character in it and return its index.
If it does not exist, return -1.

See the [first unique character in a string problem on LeetCode](https://leetcode.com/problems/first-unique-character-in-a-string).

## C++ Solution

The runtime complexity of this algorithm is $O(n)$.

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int firstUniqChar(string s) {
    vector<int> positions('z' - 'a' + 1, -1);
    vector<bool> repeats('z' - 'a' + 1, false);

    for (int i = 0; i < s.size(); ++i) {
      int offset = s[i] - 'a';

      if (positions[offset] >= 0) {
        repeats[offset] = true;
      }

      if (!repeats[offset]) {
        positions[offset] = i;
      }
    }

    int minarg = INT_MAX;
    for (int i = 0; i < repeats.size(); ++i) {
      if (!repeats[i] && positions[i] >= 0) {
        minarg = min(minarg, positions[i]);
      }
    }

    return minarg == INT_MAX ? -1 : minarg;
  }
};
```
