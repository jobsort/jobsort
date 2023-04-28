---
name: "Happy Number"
title: "LeetCode Happy Number Solution"
description: "Solution for the happy number problem from LeetCode."
published: "2021-06-30 PDT"
modified: "2021-06-30 PDT"
---

# Happy Number Problem & Solution

Write an algorithm to determine if a number `n` is happy.

A happy number is a number defined by the following process:

- Starting with any positive integer, replace the number by the sum of the squares of its digits.
- Repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1.
- Those numbers for which this process ends in 1 are happy.

Return true if `n` is a happy number, and false if not.

See the [happy number problem on LeetCode](https://leetcode.com/problems/happy-number).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isHappy(int n) {
    int slow = happy(n);
    int fast = happy(slow);

    while (slow != fast) {
      slow = happy(slow);
      fast = happy(happy(fast));
    }

    return slow == 1;
  }

private:
  int happy(int n) {
    int sum = 0;

    while (n > 0) {
      sum += pow(n % 10, 2);
      n /= 10;
    }

    return sum;
  }
};
```
