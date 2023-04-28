# Intersection of Two Arrays Problem & Solution

Given two integer arrays `nums1` and `nums2`, return an array of their intersection.
Each element in the result must be unique and you may return the result in any order.

See the [intersection of two arrays problem on LeetCode](https://leetcode.com/problems/intersection-of-two-arrays).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> intersection(vector<int>& nums1, vector<int>& nums2) {
    vector<bool> usage(1001, false);

    for (int i = 0; i < nums1.size(); ++i) {
      usage[nums1[i]] = true;
    }

    unordered_set<int> result;

    for (int i = 0; i < nums2.size(); ++i) {
      if (usage[nums2[i]]) {
        result.insert(nums2[i]);
      }
    }

    return vector<int>{result.begin(), result.end()};
  }
};
```
