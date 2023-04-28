---
name: "First Bad Version"
title: "LeetCode First Bad Version Solution"
description: "Solution for the first bad version problem from LeetCode."
published: "2021-07-13 PDT"
modified: "2021-07-13 PDT"
---

# First Bad Version Problem & Solution

You are a product manager and currently leading a team to develop a new product.
Unfortunately, the latest version of your product fails the quality check.
Since each version is developed based on the previous version, all the versions after a bad version are also bad.
Suppose you have `n` versions `[1, 2, ..., n]` and you want to find out the first bad one, which causes all the following ones to be bad.
You are given an API `bool isBadVersion(version)` which returns whether version is bad.
Implement a function to find the first bad version.
You should minimize the number of calls to the API.

See the [first bad version problem on LeetCode](https://leetcode.com/problems/first-bad-version).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

// The API isBadVersion is defined for you.
// bool isBadVersion(int version);
class Solution {
public:
  int firstBadVersion(int n) {
    int low = 0;
    int high = n;
    while (low < high) {
      int mid = low + (high - low) / 2;

      if (!isBadVersion(mid)) {
        low = mid + 1;
      } else {
        high = mid;
      }
    }

    return low;
  }
};
```
