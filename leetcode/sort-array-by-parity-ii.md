---
name: "Sort Array by Parity II"
title: "LeetCode Sort Array by Parity II Solution"
description: "Solution for given an array of integers nums, half of the integers in nums are odd, and the other half are even. Sort the array so that whenever nums[i] is odd, i is odd, and whenever nums[i] is even, i is even.Return any answer array that satisfies this condition."
published: "2021-11-29 PDT"
modified: "2021-11-29 PDT"
---

# Sort Array by Parity II Problem & Solution

Given an array of integers `nums`, half of the integers in `nums` are odd, and the other half are even.

Sort the array so that whenever `nums[i]` is odd, `i` is odd, and whenever `nums[i]` is even, `i` is even.

Return any answer array that satisfies this condition.

See the [sort array by parity ii problem on LeetCode](https://leetcode.com/problems/sort-array-by-parity-ii).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> sortArrayByParityII(vector<int>& nums) {
    int even = 0;
    int odd = 1;
    int i = 0;
    while (i < nums.size()) {
      if (nums[i] % 2 == 0 && i % 2 == 1) {
        swap(nums[i], nums[even]);
        even += 2;
      } else if (nums[i] % 2 == 1 && i % 2 == 0) {
        swap(nums[i], nums[odd]);
        odd += 2;
      } else {
        ++i;
      }
    }

    return nums;
  }
};
```
