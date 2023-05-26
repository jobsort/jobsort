# Rank Teams by Votes Problem & Solution

See the [rank teams by votes problem on LeetCode](https://leetcode.com/problems/rank-teams-by-votes).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string rankTeams(vector<string>& votes) {
    const int n = votes[0].size();
    vector<vector<int>> freq(n, vector<int>('Z' - 'A' + 1));

    for (auto vote : votes) {
      for (int i = 0; i < n; ++i) {
        ++freq[i][vote[i] - 'A'];
      }
    }

    string result = votes[0];
    sort(result.begin(), result.end(), [&](char a, char b){
      for (int i = 0; i < n; ++i) {
        if (freq[i][a - 'A'] == freq[i][b - 'A']) {
          continue;
        } else return freq[i][a - 'A'] > freq[i][b - 'A'];
      }

      return a < b;
    });

    return result;
  }
};
```
