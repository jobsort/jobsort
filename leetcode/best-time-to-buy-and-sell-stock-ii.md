# Best Time to Buy and Sell Stock II Problem & Solution

You are given an array prices where `prices[i]` is the price of a given stock on the `i`th day.

Find the maximum profit you can achieve.
You may complete as many transactions as you like (i.e., buy one and sell one share of the stock multiple times).

Note: You may not engage in multiple transactions simultaneously (i.e., you must sell the stock before you buy again).

See the [best time to buy and sell stock ii problem on LeetCode](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int maxProfit(vector<int>& prices) {
    int profit = 0;
    for (int i = 1; i < prices.size(); ++i) {
      if (prices[i - 1] < prices[i]) {
        profit += prices[i] - prices[i - 1];
      }
    }

    return profit;
  }
};
```
