---
name: "Image Smoother"
title: "LeetCode Image Smoother Solution"
description: "Solution for an image smoother is a filter of the size 3 x 3 that can be applied to each cell of an image by rounding down the average of the cell and the eight surrounding cells (i.e., the average of the nine cells in the blue smoother). If one or more of the surrounding cells of a cell is not present, we do not consider it in the average (i.e., the average of the four cells in the red smoother). Given an m x n integer matrix img representing the grayscale of an image, return the image after applying the smoother on each cell of it."
published: "2021-08-31 PDT"
modified: "2021-08-31 PDT"
---

# Image Smoother Problem & Solution

An image smoother is a filter of the size `3 x 3` that can be applied to each cell of an image by rounding down the average of the cell and the eight surrounding cells (i.e., the average of the nine cells in the blue smoother).
If one or more of the surrounding cells of a cell is not present, we do not consider it in the average (i.e., the average of the four cells in the red smoother).

Given an `m x n` integer matrix `img` representing the grayscale of an image, return the image after applying the smoother on each cell of it.

See the [image smoother problem on LeetCode](https://leetcode.com/problems/image-smoother).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> imageSmoother(vector<vector<int>>& img) {
    vector<int> x{0, -1, 1,  0, 0, -1, 1, -1,  1};
    vector<int> y{0,  0, 0, -1, 1, -1, 1,  1, -1};

    assert(x.size() == y.size());

    vector<vector<int>> result(img.size(), vector<int>(img[0].size(), 0));
    for (int i = 0; i < img.size(); ++i) {
      for (int j = 0; j < img[0].size(); ++j) {
        int sum = 0;
        int count = 0;

        for (int k = 0; k < x.size(); ++k) {
          int ii = i + x[k];
          int jj = j + y[k];
          if (ii >= 0 && ii < img.size() &&
              jj >= 0 && jj < img[0].size()) {
            sum += img[ii][jj];
            ++count;
          }
        }

        result[i][j] = sum / count;
      }
    }

    return result;
  }
};
```
