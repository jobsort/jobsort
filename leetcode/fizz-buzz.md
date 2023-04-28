# Fizz Buzz Problem & Solution

Given an integer `n`, return a string array answer (1-indexed) where:

- `answer[i] == "FizzBuzz"` if `i` is divisible by 3 and 5.
- `answer[i] == "Fizz"` if `i` is divisible by 3.
- `answer[i] == "Buzz"` if `i` is divisible by 5.
- `answer[i] == i` if non of the above conditions are true.

See the [fizz buzz problem on LeetCode](https://leetcode.com/problems/fizz-buzz).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<string> fizzBuzz(int n) {
    vector<string> result(n, "");

    for (int i = 0; i < result.size(); ++i) {
      if ((i + 1) % 3 == 0 && (i + 1) % 5 == 0) {
        result[i] = "FizzBuzz";
      } else if ((i + 1) % 3 == 0) {
        result[i] = "Fizz";
      } else if ((i + 1) % 5 == 0) {
        result[i] = "Buzz";
      } else {
        result[i] = to_string(i + 1);
      }
    }

    return result;
  }
};
```
