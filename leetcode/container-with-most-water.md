# Container with Most Water Problem & Solution

See the [container with most water problem on LeetCode](https://leetcode.com/problems/container-with-most-water).

## C++ Solution

The runtime complexity of this algorithm is $O(n)$.

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int maxArea(vector<int>& height) {
    int best = (height.size() - 1) * min(height[0], height[height.size() - 1]);

    int i = 0, j = height.size() - 1;
    while (i < j) {

      // Keeps moving the smallest height towards the center.
      if (height[i] < height[j]) {
        ++i;
      } else {
        --j;
      }

      best = max(best, (j - i) * min(height[i], height[j]));
    }

    return best;
  }
};
```
