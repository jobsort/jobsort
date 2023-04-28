---
name: "Group Anagrams"
title: "LeetCode Group Anagrams Solution"
description: "Solution for the group anagrams problem from LeetCode."
published: "2023-01-13 PDT"
modified: "2023-01-13 PDT"
---

# Group Anagrams Problem & Solution

See the [group anagrams problem on LeetCode](https://leetcode.com/problems/group-anagrams).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

class Solution {
public:
  vector<vector<string>> groupAnagrams(vector<string>& strs) {
    unordered_map<string, vector<string>> hash;
    for (string v : strs) {
      string k = v;
      sort(k.begin(), k.end());

      hash[k].push_back(v);
    }

    vector<vector<string>> results(hash.size());
    transform(hash.begin(), hash.end(), results.begin(), [](auto pair) { return pair.second; });

    return results;
  }
};
```
