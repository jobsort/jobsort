# Online Election Problem & Solution

See the [online election problem on LeetCode](https://leetcode.com/problems/online-election).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx2,bmi,bmi2")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class TopVotedCandidate {
public:
  TopVotedCandidate(vector<int>& persons, vector<int>& times) : _times(times) {
    unordered_map<int, int> counts;
    int top = persons[0];
    for (int i = 0; i < persons.size(); ++i) {
      if (++counts[persons[i]] >= counts[top]) {
        top = persons[i];
      }

      _dp[times[i]] = top;
    }
  }
    
  int q(int t) {
    return _dp[*(upper_bound(_times.begin(), _times.end(), t) - 1)];
  }

private:
  vector<int> _times;
  unordered_map<int, int> _dp;
};
```
