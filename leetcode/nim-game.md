---
name: "Nim Game"
title: "LeetCode Nim Game Solution"
description: "Solution for you are playing the following Nim Game with your friend: Initially, there is a heap of stones on the table. You and your friend will alternate taking turns, and you go first. On each turn, the person whose turn it is will remove 1 to 3 stones from the heap. The one who removes the last stone is the winner. Given n, the number of stones in the heap, return true if you can win the game assuming both you and your friend play optimally, otherwise return false."
published: "2021-07-16 PDT"
modified: "2021-08-29 PDT"
---

# Nim Game Problem & Solution

You are playing the following Nim Game with your friend:

- Initially, there is a heap of stones on the table.
- You and your friend will alternate taking turns, and you go first.
- On each turn, the person whose turn it is will remove 1 to 3 stones from the heap.
- The one who removes the last stone is the winner.

Given `n`, the number of stones in the heap, return true if you can win the game assuming both you and your friend play optimally, otherwise return false.

See the [nim game problem on LeetCode](https://leetcode.com/problems/nim-game).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool canWinNim(int n) {

    // You can always reduce a game of `n` to a game of 4.
    // If there are one to three pieces left, you can win.
    return n % 4 != 0;
  }
};
```
