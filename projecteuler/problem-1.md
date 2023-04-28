# Multiples of 3 and 5 Problem & Solution

If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9.
The sum of these multiples is 23.
Find the sum of all the multiples of 3 or 5 below 1000.

See the [multiples of 3 and 5 problem on Project Euler](https://projecteuler.net/problem=1).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

#include <iostream>
#include <vector>

using namespace std;

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

int main() {
  int sum = 0;
  for (int i = 0; i < 1000; ++i) {
    if (i % 3 == 0 || i % 5 == 0) {
      sum += i;
    }
  }

  cout << sum << endl;
}
```
