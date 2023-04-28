---
name: "Distribute Candies"
title: "LeetCode Distribute Candies Solution"
description: "Solution for the distribute candies problem from LeetCode."
published: "2021-07-22 PDT"
modified: "2021-07-22 PDT"
---

# Distribute Candies Problem & Solution

Alice has `n` candies, where the ith candy is of type `candyType[i]`.
Alice noticed that she started to gain weight, so she visited a doctor.

The doctor advised Alice to only eat `n / 2` of the candies she has (`n` is always even).
Alice likes her candies very much, and she wants to eat the maximum number of different types of candies while still following the doctor's advice.

Given the integer array `candyType` of length `n`, return the maximum number of different types of candies she can eat if she only eats `n / 2` of them.

See the [distribute candies problem on LeetCode](https://leetcode.com/problems/distribute-candies).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int distributeCandies(vector<int>& candyType) {
    unordered_set<int> uniques;

    for (int i = 0; i < candyType.size(); ++i) {
      uniques.insert(candyType[i]);
    }

    return min(uniques.size(), candyType.size() / 2);
  }
};
```
