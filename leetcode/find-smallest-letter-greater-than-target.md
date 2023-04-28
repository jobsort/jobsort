---
name: "Find Smallest Letter Greater Than Target"
title: "LeetCode Find Smallest Letter Greater Than Target Solution"
description: "Solution for given a characters array letters that is sorted in non-decreasing order and a character target, return the smallest character in the array that is larger than target. Note that the letters wrap around. For example, if target == 'z' and letters == ['a', 'b'], the answer is 'a'."
published: "2021-09-02 PDT"
modified: "2021-09-02 PDT"
---

# Find Smallest Letter Greater Than Target Problem & Solution

Given a characters array `letters` that is sorted in non-decreasing order and a character `target`, return the smallest character in the array that is larger than `target`.

Note that the letters wrap around.

For example, if `target == 'z'` and `letters == ['a', 'b']`, the answer is `'a'`.

See the [find smallest letter greater than target problem on LeetCode](https://leetcode.com/problems/find-smallest-letter-greater-than-target).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  char nextGreatestLetter(vector<char>& letters, char target) {
    int low = 0;
    int high = letters.size() - 1;
    while (low < high) {
      int mid = low + (high - low) / 2;
      if (letters[mid] < target) {
        low = mid + 1;
      } else {
        high = mid;
      }
    }

    if (letters[low] == target) {
      while (low < letters.size() && letters[low] == target) {
        ++low;
      }

      return letters[low < letters.size() ? low : 0];
    } else if (letters[low] > target) {
      return letters[low];
    } else {
      return letters[0];
    }
  }
};
```
