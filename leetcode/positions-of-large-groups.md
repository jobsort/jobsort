# Positions of Large Groups Problem & Solution

In a string `s` of lowercase letters, these letters form consecutive groups of the same character.

For example, a string like `s = "abbxxxxzyy"` has the groups `"a"`, `"bb"`, `"xxxx"`, `"z"`, and `"yy"`.

A group is identified by an interval `[start, end]`, where `start` and `end` denote the start and end indices (inclusive) of the group.
In the above example, `"xxxx"` has the interval `[3,6]`.

A group is considered large if it has 3 or more characters.

Return the intervals of every large group sorted in increasing order by start index.

See the [positions of large groups problem on LeetCode](https://leetcode.com/problems/positions-of-large-groups).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("fast-math")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> largeGroupPositions(string s) {
    vector<vector<int>> result;

    int i = 0;
    for (int j = 1; j <= s.size(); ++j) {
      if (j == s.size() || s[i] != s[j]) {
        i = j;
      }

      if (j - i >= 2) {
        if (result.size() > 0 &&
            result.back()[0] == i) {
          result.back()[1] = j;
        } else {
          result.push_back({i, j});
        }
      }
    }

    return result;
  }
};
```
