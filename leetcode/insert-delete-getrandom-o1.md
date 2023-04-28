---
name: "Insert Delete GetRandom O(1)"
title: "LeetCode Insert Delete GetRandom O(1) Solution"
description: "Solution for the insert delete getrandom O(1) problem from LeetCode."
published: "2023-02-13 PDT"
modified: "2023-02-13 PDT"
---

# Insert Delete GetRandom O(1) Problem & Solution

See the [insert delete getrandom O(1) problem on LeetCode](https://leetcode.com/problems/insert-delete-getrandom-o1).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC taget("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class RandomizedSet {
public:
  RandomizedSet() {
    // noop
  }
  
  bool insert(int val) {
    if (hash.find(val) == hash.end()) {
      vect.push_back(val);
      hash[val] = vect.size() - 1;

      return true;
    }

    return false;
  }

  bool remove(int val) {
    auto node = hash.find(val);
    if (node != hash.end()) {
      int pos = node->second;

      swap(vect[pos], vect.back());
      hash[vect[pos]] = pos;

      vect.erase(vect.end() - 1);
      hash.erase(node);

      return true;
    }

    return false;
  }
  
  int getRandom() {
    return vect[rand() % vect.size()];
  }

private:
  vector<int> vect;
  unordered_map<int, int> hash;
};
```
