# Add Binary Problem & Solution

Given two binary strings `a` and `b`, return their sum as a binary string.

See the [add binary problem on LeetCode](https://leetcode.com/problems/add-binary).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string addBinary(string a, string b) {
    int longest = max(a.size(), b.size());
    string sum(longest, '0');

    int i = a.size() - 1;
    int j = b.size() - 1;
    int k = longest - 1;
    int carryover = 0;
    while (i >= 0 && j >= 0) {
      int ci = a[i--] == '1' ? 1 : 0;
      int cj = b[j--] == '1' ? 1 : 0;
      sum[k--] = (ci + cj + carryover) % 2 + '0';
      carryover = (ci + cj + carryover) / 2;
    }

    while (i >= 0) {
      int ci = a[i--] == '1' ? 1 : 0;
      sum[k--] = (ci + carryover) % 2 + '0';
      carryover = (ci + carryover) / 2;
    }

    while (j >= 0) {
      int cj = b[j--] == '1' ? 1 : 0;
      sum[k--] = (cj + carryover) % 2 + '0';
      carryover = (cj + carryover) / 2;
    }

    if (carryover > 0) {
      sum.insert(0, "1");
    }

    return sum;
  }
};
```
