---
name: "Distance between Bus Stops"
title: "LeetCode Distance between Bus Stops Solution"
description: "Solution for a bus has n stops numbered from 0 to n - 1 that form a circle. We know the distance between all pairs of neighboring stops where distance[i] is the distance between the stops number i and (i + 1) % n. The bus goes along both directions i.e. clockwise and counterclockwise. Return the shortest distance between the given start and destination stops."
published: "2021-12-28 PDT"
modified: "2021-12-28 PDT"
---

# Distance between Bus Stops Problem & Solution

A bus has `n` stops numbered from `0` to `n - 1` that form a circle.
We know the distance between all pairs of neighboring stops where `distance[i]` is the distance between the stops number `i` and `(i + 1) % n`.

The bus goes along both directions i.e. clockwise and counterclockwise.

Return the shortest distance between the given `start` and `destination` stops.

See the [distance between bus stops problem on LeetCode](https://leetcode.com/problems/distance-between-bus-stops).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int distanceBetweenBusStops(vector<int>& distance, int start, int destination) {
    int clockwise = 0;
    int node = start;
    while (node != destination) {
      clockwise += distance[node];
      node = (node + 1) % distance.size();
    }

    int counterclockwise = 0;
    node = destination;
    while (node != start) {
      counterclockwise += distance[node];
      node = (node + 1) % distance.size();
    }

    return min(clockwise, counterclockwise);
  }
};
```
