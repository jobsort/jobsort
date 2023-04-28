# K Closest Points to Origin Problem & Solution

See the [k closest points to origin problem on LeetCode](https://leetcode.com/problems/k-closest-points-to-origin).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<vector<int>> kClosest(vector<vector<int>>& points, int k) {
    priority_queue<pair<float, int>> pq;

    for (int i = 0; i < points.size(); ++i) {
      float d = pow(points[i][0], 2) + pow(points[i][1], 2);

      pq.push({d, i});
      if (pq.size() > k) {
        pq.pop();
      }
    }

    vector<vector<int>> results;
    while (!pq.empty()) {
      results.push_back(points[pq.top().second]);
      pq.pop();
    }

    return results;
  }
};
```
