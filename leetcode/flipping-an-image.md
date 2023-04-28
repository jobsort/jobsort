# Flipping an Image Problem & Solution

Given an `n x n` binary matrix image, flip the image horizontally, then invert it, and return the resulting image.

To flip an image horizontally means that each row of the image is reversed.
For example, flipping `[1,1,0]` horizontally results in `[0,1,1]`.

To invert an image means that each `0` is replaced by `1`, and each `1` is replaced by `0`. For example, inverting `[0,1,1]` results in `[1,0,0]`.

See the [flipping an image problem on LeetCode](https://leetcode.com/problems/flipping-an-image).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("fast-math")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> flipAndInvertImage(vector<vector<int>>& image) {
    for (int i = 0; i < image.size(); ++i) {
      for (int j = 0; j < image[i].size() / 2; ++j) {
        int k = image[i].size() - j - 1;
        swap(image[i][j], image[i][k]);
      }

      for (int j = 0; j < image[i].size(); ++j) {
        image[i][j] = 1 - image[i][j];
      }
    }

    return image;
  }
};
```
