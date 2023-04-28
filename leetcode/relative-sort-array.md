# Relative Sort Array Problem & Solution

See the [relative sort array problem on LeetCode](https://leetcode.com/problems/relative-sort-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> relativeSortArray(vector<int>& arr1, vector<int>& arr2) {
    unordered_map<int, int> freq;
    for (int a : arr2) {
      freq[a] = 0;
    }
    for (int a : arr1) {
      if (freq.find(a) != freq.end()) {
        ++freq[a];
      }
    }

    vector<int> results(arr1.size());
    int i = 0;
    for (int a : arr2) {
      for (int j = 0; j < freq[a]; ++j) {
        results[i++] = a;
      }
    }

    int offset = i;
    for (int a : arr1) {
      if (freq.find(a) == freq.end()) {
        results[i++] = a;
      }
    }

    sort(results.begin() + offset, results.end());

    return results;
  }
};
```
