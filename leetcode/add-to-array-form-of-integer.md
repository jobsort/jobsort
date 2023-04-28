---
name: "Add to Array-Form of Integer"
title: "LeetCode Add to Array-Form of Integer Solution"
description: "Solution for the array-form of an integer num is an array representing its digits in left to right order. For example, for num = 1321, the array form is [1,3,2,1]. Given num, the array-form of an integer, and an integer k, return the array-form of the integer num + k."
published: "2021-12-19 PDT"
modified: "2021-12-19 PDT"
---

# Add to Array-Form of Integer Problem & Solution

The array-form of an integer `num` is an array representing its digits in left to right order.

For example, for `num = 1321`, the array form is `[1,3,2,1]`.
Given `num`, the array-form of an integer, and an integer `k`, return the array-form of the integer `num + k`.

See the [add to array-form of integer problem on LeetCode](https://leetcode.com/problems/add-to-array-form-of-integer).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("fast-math")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> addToArrayForm(vector<int>& num, int k) {
    int carry = 0;
    int i = 0;
    while (k > 0 || carry > 0) {
      if (i == num.size()) {
        num.insert(num.begin(), 0);
      }

      int j = num.size() - i - 1;
      int digit = k % 10;
      int sum = num[j] + digit + carry;
      k /= 10;
      num[j] = sum % 10;
      carry = sum / 10;

      ++i;
    }

    return num;
  }
};
```
