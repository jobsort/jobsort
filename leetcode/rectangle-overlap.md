# Rectangle Overlap Problem & Solution

An axis-aligned rectangle is represented as a list `[x1, y1, x2, y2]`, where `(x1, y1)` is the coordinate of its bottom-left corner, and `(x2, y2)` is the coordinate of its top-right corner.
Its top and bottom edges are parallel to the X-axis, and its left and right edges are parallel to the Y-axis.

Two rectangles overlap if the area of their intersection is positive.
To be clear, two rectangles that only touch at the corner or edges do not overlap.

Given two axis-aligned rectangles `rec1` and `rec2`, return `true` if they overlap, otherwise return `false`.

See the [rectangle overlap problem on LeetCode](https://leetcode.com/problems/rectangle-overlap).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isRectangleOverlap(vector<int>& rec1, vector<int>& rec2) {
    int x1 = rec1[0];
    int y1 = rec1[1];
    int x2 = rec1[2];
    int y2 = rec1[3];

    int x3 = rec2[0];
    int y3 = rec2[1];
    int x4 = rec2[2];
    int y4 = rec2[3];

    // Tests if the second rectangle is to the left, right, top, or bottom of the first.
    return !(y4 <= y1 || y2 <= y3 || x2 <= x3 || x4 <= x1);
  }
};
```
