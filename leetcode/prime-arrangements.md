# Prime Arrangements Problem & Solution

See the [prime arrangements problem on LeetCode](https://leetcode.com/problems/prime-arrangements).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int numPrimeArrangements(int n) {
    vector<bool> primes(n + 1, true);
    primes[1] = false;

    int i = 2;
    while (i <= sqrt(n)) {
      if (primes[i]) {
        for (int j = i * 2; j <= n; j += i) {
          primes[j] = false;
        }
      }

      ++i;
    }

    long result = 1;
    int modulo = 1'000'000'007;

    int primes_so_far = 0;
    for (int i = 1; i <= n; ++i) {
      if (primes[i]) {
        result = (result * ++primes_so_far) % modulo;
      } else {
        result = (result * (i - primes_so_far)) % modulo;
      }
    }

    return result;
  }
};
```
