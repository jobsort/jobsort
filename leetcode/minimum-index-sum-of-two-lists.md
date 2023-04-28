# Minimum Index Sum of Two Lists Problem & Solution

See the [minimum index sum of two lists problem on LeetCode](https://leetcode.com/problems/minimum-index-sum-of-two-lists).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<string> findRestaurant(vector<string>& list1, vector<string>& list2) {
    unordered_map<string, int> hash;
    for (int i = 0; i < list1.size(); ++i) {
      hash[list1[i]] = i;
    }

    int sum = list1.size() + list2.size();
    for (int i = 0; i < list2.size(); ++i) {
      if (hash.find(list2[i]) != hash.end()) {
        sum = min(sum, hash[list2[i]] + i);
      }
    }

    vector<string> result;
    for (int i = 0; i < list2.size(); ++i) {
      if (hash.find(list2[i]) != hash.end() &&
          hash[list2[i]] + i == sum) {
        result.push_back(list2[i]);
      }
    }

    return result;
  }
};
```
