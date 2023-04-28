---
name: "Best Time to Buy and Sell Stock"
title: "LeetCode Best Time to Buy and Sell Stock Solution"
description: "Solution for the best time to buy and sell stock problem from LeetCode."
published: "2021-06-09 PDT"
modified: "2021-06-10 PDT"
---

# Best Time to Buy and Sell Stock Problem & Solution

You are given an array `prices` where `prices[i]` is the price of a given stock on the `i`th day.
You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.
Return the maximum profit you can achieve from this transaction.
If you cannot achieve any profit, return 0.

See the [best time to buy and sell stock problem on LeetCode](https://leetcode.com/problems/best-time-to-buy-and-sell-stock).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int maxProfit(vector<int>& prices) {
    int min_value = INT_MAX;
    int result = 0;

    for (int i = 0; i < prices.size(); ++i) {
      if (min_value > prices[i]) {
        min_value = prices[i];
      } else if (prices[i] - min_value > result) {
        result = prices[i] - min_value;
      }
    }

    return result;
  }
};
```
