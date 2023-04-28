---
name: "Guess Number Higher or Lower"
title: "LeetCode Guess Number Higher or Lower Solution"
description: "Solution for the guess number higher or lower problem from LeetCode."
published: "2021-07-06 PDT"
modified: "2021-07-06 PDT"
---

# Guess Number Higher or Lower Problem & Solution

We are playing the Guess Game. The game is as follows:

I pick a number from 1 to `n`.
You have to guess which number I picked.
Every time you guess wrong, I will tell you whether the number I picked is higher or lower than your guess.
You call a pre-defined API `int guess(int num)`, which returns 3 possible results:

- -1: The number I picked is lower than your guess (i.e. `pick < num`).
- 1: The number I picked is higher than your guess (i.e. `pick > num`).
- 0: The number I picked is equal to your guess (i.e. `pick == num`).

Return the number that I picked.

See the [guess number higher or lower problem on LeetCode](https://leetcode.com/problems/guess-number-higher-or-lower).

## C++ Solution

The runtime complexity of the algorithm is $O(\log{}n)$.

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

/**
 * Forward declaration of guess API.
 * @param  num   your guess
 * @return 	     -1 if num is lower than the guess number
 *			         1 if num is higher than the guess number
 *               otherwise return 0
 * int guess(int num);
 */
class Solution {
public:
  int guessNumber(int n) {
    int low = 1;
    int high = n;
    while (low < high) {
      int mid = low + (high - low) / 2;
      int result = guess(mid);

      if (result == 0) {
        return mid;
      } else if (result > 0) {
        low = mid + 1;
      } else {
        high = mid;
      }
    }

    return low;
  }
};
```
