# Largest Prime Factor Problem & Solution

The prime factors of 13195 are 5, 7, 13 and 29.
What is the largest prime factor of the number 600851475143?

See the [largest prime factor problem on Project Euler](https://projecteuler.net/problem=3).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

#include <iostream>

using namespace std;

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

int main() {
  long n = 600851475143;

  int result = 0;
  int i = 2;
  while (n > 1) {
    while (n % i == 0) {
      n /= i;
      result = max(result, i);
    }

    ++i;
  }

  cout << result << endl;
}
```
