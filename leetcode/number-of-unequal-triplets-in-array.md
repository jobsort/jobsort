# Number of Unequal Triplets in Array Problem & Solution

See the [number of unequal triplets in array problem on LeetCode](https://leetcode.com/problems/number-of-unequal-triplets-in-array).

## C++ Solution 1

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int unequalTriplets(vector<int>& nums) {
    sort(nums.begin(), nums.end());

    int result = 0;
    for (int i = 0; i < nums.size() - 2; ++i) {
      for (int j = i + 1; j < nums.size() - 1; ++j) {
        if (nums[j] == nums[i]) { continue; }

        for (int k = j + 1; k < nums.size(); ++k) {
          if (nums[k] == nums[j]) { continue; }

          ++result;
        }
      }
    }

    return result;
  }
};
```

## C++ Solution 2

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int unequalTriplets(vector<int>& nums) {
    map<int, int> freq;
    for (int x : nums) {
      ++freq[x];
    }

    int result = 0;
    int left = 0, right = nums.size(); // sum of freq counts
    for (auto [x, count] : freq) {
      right -= count;
      result += left * count * right;
      left += count;
    }

    return result;
  }
};
```