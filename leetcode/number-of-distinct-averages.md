---
name: "Number of Distinct Averages"
title: "LeetCode Number of Distinct Averages Solution"
description: "Solution for you are given a 0-indexed integer array nums of even length. As long as nums is not empty, you must repetitively: Find the minimum number in nums and remove it. Find the maximum number in nums and remove it. Calculate the average of the two removed numbers. The average of two numbers a and b is (a + b) / 2. For example, the average of 2 and 3 is (2 + 3) / 2 = 2.5. Return the number of distinct averages calculated using the above process. Note that when there is a tie for a minimum or maximum number, any can be removed."
published: "2022-11-21 PDT"
modified: "2022-11-21 PDT"
---

# Number of Distinct Averages Problem & Solution

You are given a 0-indexed integer array `nums` of even length.

As long as `nums` is not empty, you must repetitively:

- Find the minimum number in `nums` and remove it.
- Find the maximum number in `nums` and remove it.
- Calculate the average of the two removed numbers.

The average of two numbers `a` and `b` is `(a + b) / 2`.

For example, the average of 2 and 3 is (2 + 3) / 2 = 2.5.
Return the number of distinct averages calculated using the above process.

Note that when there is a tie for a minimum or maximum number, any can be removed.

See the [number of distinct averages problem on LeetCode](https://leetcode.com/problems/number-of-distinct-averages).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int distinctAverages(vector<int>& nums) {
    sort(nums.begin(), nums.end()); // nlogn
    set<float> unique; // logn
    int i = 0, j = nums.size() - 1;
    while (i < j) {
      unique.insert((nums[i] + nums[j]) / 2.0);
      ++i;
      --j;
    }

    return unique.size();
  }
};
```
