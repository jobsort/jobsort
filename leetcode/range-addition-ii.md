# Range Addition II Problem & Solution

See the [range addition ii problem on LeetCode](https://leetcode.com/problems/range-addition-ii).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int maxCount(int m, int n, vector<vector<int>>& ops) {
    int mm = m, nn = n;
    for (int i = 0; i < ops.size(); ++i) {
      mm = min(mm, ops[i][0]);
      nn = min(nn, ops[i][1]);
    }
    
    return mm * nn;
  }
};
```
