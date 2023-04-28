---
name: "Count Primes"
title: "LeetCode Count Primes Solution"
description: "Solution for the count primes problem from LeetCode."
published: "2021-06-28 PDT"
modified: "2021-06-28 PDT"
---

# Count Primes Problem & Solution

Count the number of prime numbers less than a non-negative number, `n`.

See the [count primes problem on LeetCode](https://leetcode.com/problems/count-primes).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int countPrimes(int n) {
    if (n < 2) {
      return 0;
    }

    vector<bool> sieve(n, true);
    sieve[0] = false;
    sieve[1] = false;

    for (int i = 2; i < n; ++i) {
      if (sieve[i]) {
        for (int j = i * 2; j < n; j += i) {
          sieve[j] = false;
        }
      }
    }

    int result = 0;
    for (int i = 2; i < n; ++i) {
      if (sieve[i]) {
        result += 1;
      }
    }

    return result;
  }
};
```
