# Largest Triangle Area Problem & Solution

Given an array of points on the X-Y plane points where `points[i] = [xi, yi]`, return the area of the largest triangle that can be formed by any three different points.
Answers within `10^-5` of the actual answer will be accepted.

See the [largest triangle area problem on LeetCode](https://leetcode.com/problems/largest-triangle-area).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("fast-math")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  double largestTriangleArea(vector<vector<int>>& points) {
    double largest = 0;

    for (int i = 0; i < points.size() - 2; ++i) {
      for (int j = i + 1; j < points.size() - 1; ++j) {
        for (int k = j + 1; k < points.size(); ++k) {
          double area = abs(0.5 * (points[i][0] * (points[j][1] - points[k][1]) + points[j][0] * (points[k][1] - points[i][1]) + points[k][0] * (points[i][1] - points[j][1])));

          largest = max(largest, area);
        }
      }
    }

    return largest;
  }
};
```
