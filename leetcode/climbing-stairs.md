# Climbing Stairs Problem & Solution

You are climbing a staircase.
It takes `n` steps to reach the top.
Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

See the [climbing stairs problem on LeetCode](https://leetcode.com/problems/climbing-stairs).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int climbStairs(int n) {
    if (n <= 2) {
      return n;
    }

    int result = 0;
    int first = 1;
    int second = 2;

    for (int i = 3; i <= n; ++i) {
      int tmp = result;

      result = first + second;
      first = second;
      second = result;
    }

    return result;
  }
};
```
