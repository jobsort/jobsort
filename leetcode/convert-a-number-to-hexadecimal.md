# Convert a Number to Hexadecimal Problem & Solution

Given an integer `num`, return a string representing its hexadecimal representation.
For negative integers, two’s complement method is used.

All the letters in the answer string should be lowercase characters, and there should not be any leading zeros in the answer except for the zero itself.

Note: You are not allowed to use any built-in library method to directly solve this problem.

See the [convert a number to hexadecimal problem on LeetCode](https://leetcode.com/problems/convert-a-number-to-hexadecimal).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string toHex(int num) {
    if (num == 0) {
      return "0";
    }

    string result = "";

    // Converts to two's complement.
    uint unum = (uint)num;

    while (unum > 0) {
      int r = unum % 16;
      result += r < 10 ? r + '0' : r - 10 + 'a';
      unum /= 16;
    }

    reverse(result.begin(), result.end());

    return result;
  }
};
```
