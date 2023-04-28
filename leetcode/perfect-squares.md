# Perfect Squares Problem & Solution

See the [perfect squares problem on LeetCode](https://leetcode.com/problems/perfect-squares).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("fast-math")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int numSquares(int n) {
    vector<int> dp(n + 1, numeric_limits<int>::max());
    dp[0] = 0;
    dp[1] = 1;

    for (int i = 0; i <= n; ++i) {
      int j = 1;
      while (i + j * j < dp.size()) {
        dp[i + j * j] = min(dp[i + j * j], dp[i] + 1);
        ++j;
      }
    }

    return dp[n];
  }
};
```
