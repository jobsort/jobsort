---
name: "Top K Frequent Elements"
title: "LeetCode Top K Frequent Elements Solution"
description: "Solution for the top k frequent elements problem from LeetCode."
published: "2023-03-06 PDT"
modified: "2023-03-06 PDT"
---

# Top K Frequent Elements Problem & Solution

See the [top k frequent elements problem on LeetCode](https://leetcode.com/problems/top-k-frequent-elements).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> topKFrequent(vector<int>& nums, int k) {
    unordered_map<int, int> freq;
    for (auto num : nums) { // O(n)
      ++freq[num]; // O(1)
    }

    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;
    for (auto [q, v] : freq) { // O(n)
      pq.push({v, q}); // O(logn)

      if (pq.size() > k) { // O(1)
        pq.pop(); // O(1)
      }
    }

    vector<int> results;
    while (!pq.empty()) { // O(n)
      results.push_back(pq.top().second); // O(1)
      pq.pop(); // O(1)
    }

    return results;
  }
};
```
