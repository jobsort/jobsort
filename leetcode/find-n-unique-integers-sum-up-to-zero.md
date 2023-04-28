# Find N Unique Integers Sum up to Zero Problem & Solution

See the [find n unique integers sum up to zero problem on LeetCode](https://leetcode.com/problems/find-n-unique-integers-sum-up-to-zero).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> sumZero(int n) {
    vector<int> result(n);
    int sum = 0;

    for (int i = 0; i < n - 1; ++i) {
      sum += i + 1;
      result[i] = i + 1;
    }

    result.back() = -sum;

    return result;
  }
};
```
