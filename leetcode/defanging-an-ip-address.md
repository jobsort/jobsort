---
name: "Defanging an IP Address"
title: "LeetCode Defanging an IP Address Solution"
description: "Solution for the defanging an IP address problem from LeetCode."
published: "2023-01-05 PDT"
modified: "2023-01-05 PDT"
---

# Defanging an IP Address Problem & Solution

See the [defanging an IP address problem on LeetCode](https://leetcode.com/problems/defanging-an-ip-address).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string defangIPaddr(string address) {
    string dot = ".";

    int i = 0, j;
    while ((j = address.find(dot, i)) != string::npos) {
      address.replace(j, dot.size(), "[.]");
      i = j + 3;
    }

    return address;
  }
};
```
