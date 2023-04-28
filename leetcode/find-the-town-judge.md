---
name: "Find the Town Judge"
title: "LeetCode Find the Town Judge Solution"
description: "Solution for In a town, there are n people labeled from 1 to n. There is a rumor that one of these people is secretly the town judge. If the town judge exists, then: The town judge trusts nobody. Everybody (except for the town judge) trusts the town judge. There is exactly one person that satisfies properties 1 and 2. You are given an array trust where trust[i] = [ai, bi] representing that the person labeled ai trusts the person labeled bi. Return the label of the town judge if the town judge exists and can be identified, or return -1 otherwise."
published: "2021-12-26 PDT"
modified: "2021-12-27 PDT"
---

# Find the Town Judge Problem & Solution

In a town, there are `n` people labeled from `1` to `n`.
There is a rumor that one of these people is secretly the town judge.

If the town judge exists, then:

- The town judge trusts nobody.
- Everybody (except for the town judge) trusts the town judge.
- There is exactly one person that satisfies properties 1 and 2.

You are given an array trust where `trust[i] = [ai, bi]` representing that the person labeled `ai` trusts the person labeled `bi`.

Return the label of the town judge if the town judge exists and can be identified, or return `-1` otherwise.

See the [find the town judge problem on LeetCode](https://leetcode.com/problems/find-the-town-judge).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int findJudge(int n, vector<vector<int>>& trust) {
    vector<int> incoming(n, 0);
    vector<int> outgoing(n, 0);
    for (int i = 0; i < trust.size(); ++i) {
      ++incoming[trust[i][1] - 1];
      ++outgoing[trust[i][0] - 1];
    }

    for (int i = 0; i < n; ++i) {
      if (incoming[i] == n - 1 &&
          outgoing[i] == 0) {
        return i + 1;
      }
    }

    return -1;
  }
};
```
