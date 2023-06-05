# Top K Frequent Words Problem & Solution

See the [top k frequent words problem on LeetCode](https://leetcode.com/problems/top-k-frequent-words).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<string> topKFrequent(vector<string>& words, int k) {
    unordered_map<string, int> freq;
    for (auto word : words) {
      ++freq[word];
    }

    vector<string> unique;
    for (auto [k, v] : freq) {
      unique.push_back(k);
    }

    // O(nlogk)
    partial_sort(unique.begin(), unique.begin() + k, unique.end(), [&](auto a, auto b) {
      if (freq[a] == freq[b]) {
        return a < b;
      } else {
        return freq[a] > freq[b];
      }
    });

    vector<string> result(unique.begin(), unique.begin() + k);

    return result;
  }
};
```
