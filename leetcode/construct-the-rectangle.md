---
name: "Construct the Rectangle"
title: "LeetCode Construct the Rectangle Solution"
description: "Solution for a web developer needs to know how to design a web page's size. So, given a specific rectangular web page's area, your job by now is to design a rectangular web page, whose length L and width W satisfy the following requirements: The area of the rectangular web page you designed must equal to the given target area. The width W should not be larger than the length L, which means L >= W. The difference between length L and width W should be as small as possible. Return an array [L, W] where L and W are the length and width of the web page you designed in sequence."
published: "2021-08-06 PDT"
modified: "2021-08-06 PDT"
---

# Construct the Rectangle Problem & Solution

A web developer needs to know how to design a web page's size.
So, given a specific rectangular web page's area, your job by now is to design a rectangular web page, whose length `L` and width `W` satisfy the following requirements:

- The area of the rectangular web page you designed must equal to the given target area.
- The width `W` should not be larger than the length `L`, which means `L >= W`.
- The difference between length `L` and width `W` should be as small as possible.

Return an array `[L, W]` where `L` and `W` are the length and width of the web page you designed in sequence.

See the [construct the rectangle problem on LeetCode](https://leetcode.com/problems/construct-the-rectangle).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> constructRectangle(int area) {

    // Starts with the square root and keeps decrementing to find an exact match.
    for (int i = sqrt(area); i > 0; --i) {
      if (area % i == 0) {

        // The denominator keeps getting smaller, so `area / i` will be larger.
        return {area / i, i};
      }
    }

    // If the area is a prime number, return itself because it's the only way to decompose.
    return {area, 1};
  }
};
```
