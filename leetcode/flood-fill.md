---
name: "Flood Fill"
title: "LeetCode Flood Fill Solution"
description: "Solution for an image is represented by an m x n integer grid image where image[i][j] represents the pixel value of the image. You are also given three integers sr, sc, and newColor. You should perform a flood fill on the image starting from the pixel image[sr][sc]. To perform a flood fill, consider the starting pixel, plus any pixels connected 4-directionally to the starting pixel of the same color as the starting pixel, plus any pixels connected 4-directionally to those pixels (also with the same color), and so on. Replace the color of all of the aforementioned pixels with newColor. Return the modified image after performing the flood fill."
published: "2021-08-17 PDT"
modified: "2021-08-17 PDT"
---

# Flood Fill Problem & Solution

An image is represented by an `m` x `n` integer grid image where `image[i][j]` represents the pixel value of the image.

You are also given three integers `sr`, `sc`, and `newColor`.
You should perform a flood fill on the image starting from the pixel `image[sr][sc]`.

To perform a flood fill, consider the starting pixel, plus any pixels connected 4-directionally to the starting pixel of the same color as the starting pixel, plus any pixels connected 4-directionally to those pixels (also with the same color), and so on.
Replace the color of all of the aforementioned pixels with `newColor`.

Return the modified image after performing the flood fill.

See the [flood fill problem on LeetCode](https://leetcode.com/problems/flood-fill).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC optimization("max-inline-insns-recursive-auto")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> floodFill(vector<vector<int>>& image, int sr, int sc, int newColor) {

    // Must check if the color to be replaced is different than `newColor`; otherwise,
    // the algorithm goes into an infinite loop as we don't keep track of visited cells.
    int oldColor = image[sr][sc];
    if (oldColor != newColor) {
      floodFill(image, sr, sc, oldColor, newColor);
    }

    return image;
  }

private:
  void floodFill(vector<vector<int>>& image, int i, int j, int oldColor, int newColor) {
    image[i][j] = newColor;

    vector<int> x{0, 0, -1, +1};
    vector<int> y{-1, +1, 0, 0};

    assert(x.size() == y.size());
    for (int k = 0; k < x.size(); ++k) {
      int ix = i + x[k];
      int jy = j + y[k];

      if (ix >= 0 && ix < image.size() &&
          jy >= 0 && jy < image[ix].size() &&
          image[ix][jy] == oldColor) {
        floodFill(image, ix, jy, oldColor, newColor);
      }
    }
  }
};
```
