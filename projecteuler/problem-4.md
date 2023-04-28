# Largest Palindrome Product Problem & Solution

A palindromic number reads the same both ways.
The largest palindrome made from the product of two 2-digit numbers is 9009 = 91 \* 99.
Find the largest palindrome made from the product of two 3-digit numbers.

See the [largest palindrome product problem on Project Euler](https://projecteuler.net/problem=4).

## C++ Solution

The runtime complexity of this algorithm is $O(n^2)$.

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

#include <iostream>

using namespace std;

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

bool is_palindrome(int n) {
  int m = 0;
  int tmp = n;
  while (tmp > 0) {
    m = m * 10 + tmp % 10;
    tmp /= 10;
  }

  return m == n;
}

int largest_palindrome() {
  int result = 0;

  for (int i = 999; i >= 100; --i) {
    for (int j = i; j >= 100; --j) {
      int product = i * j;
      if (is_palindrome(product)) {
        result = max(result, product);
      }
    }
  }

  return result;
}

int main() {
  cout << largest_palindrome() << endl;
}
```
