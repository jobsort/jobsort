---
name: "Min Cost Climbing Stairs"
title: "LeetCode Min Cost Climbing Stairs Solution"
description: "Solution for you are given an integer array cost where cost[i] is the cost of ith step on a staircase. Once you pay the cost, you can either climb one or two steps. You can either start from the step with index 0, or the step with index 1. Return the minimum cost to reach the top of the floor."
published: "2021-08-23 PDT"
modified: "2021-08-23 PDT"
---

# Min Cost Climbing Stairs Problem & Solution

You are given an integer array `cost` where `cost[i]` is the cost of ith step on a staircase.
Once you pay the cost, you can either climb one or two steps.

You can either start from the step with index 0, or the step with index 1.

Return the minimum cost to reach the top of the floor.

See the [min cost climbing stairs problem on LeetCode](https://leetcode.com/problems/min-cost-climbing-stairs).

## C++ Solution

The runtime complexity of this algorithm is $O(n)$.

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int minCostClimbingStairs(vector<int>& cost) {

    // Note that the length of the `total` vector is larger by one compared to the `cost` vector.
    vector<int> total(cost.size() + 1, 0);
    total[0] = cost[0];
    total[1] = cost[1];

    for (int i = 2; i < total.size(); ++i) {

      // Takes the minimum total from the `i - 1`th and `i - 2`th step, and adds up the current cost.
      total[i] = min(total[i - 1], total[i - 2]) +
        (i < cost.size() ? cost[i] : 0);
    }

    return total[total.size() - 1];
  }
};
```
