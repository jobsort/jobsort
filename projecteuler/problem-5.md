# Smallest Multiple Problem & Solution

2520 is the smallest number that can be divided by each of the numbers from 1 to 10 without any remainder.
What is the smallest positive number that is evenly divisible by all of the numbers from 1 to 20?

See the [smallest multiple problem on Project Euler](https://projecteuler.net/problem=5).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")

#include <iostream>

using namespace std;

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

int main() {

  // You can do this problem by hand; there is no point in writing an algorithm.
  cout << 19 * 17 * 16 * 13 * 11 * 9 * 7 * 5 << endl;
}
```
