# Count Square Sum Triples Problem & Solution

See the [count square sum triples problem on LeetCode](https://leetcode.com/problems/count-square-sum-triples).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int countTriples(int n) {
    int result = 0;
    for (int a = 1; a <= n; ++a) {
      for (int b = a + 1; b <= n; ++b) {
        int sum = a * a + b * b;
        int c = sqrt(sum);
        if (c <= n && c * c == sum) {
          result += 2;
        } else if (sum > n * n) {
          break;
        }
      }
    }

    return result;
  }
};
```
