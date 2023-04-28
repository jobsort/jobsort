# Take Gifts from the Richest Pile Problem & Solution

See the [take gifts from the richest pile problem on LeetCode](https://leetcode.com/problems/take-gifts-from-the-richest-pile).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  long long pickGifts(vector<int>& gifts, int k) {
    priority_queue<int> pq(gifts.begin(), gifts.end());

    for (int i = 0; i < k; ++i) {
      int top = pq.top();
      pq.pop();

      top = floor(sqrt(top));
      pq.push(top);
    }

    long long result = 0;
    while (pq.size() > 0) {
      result += pq.top();
      pq.pop();
    }

    return result;
  }
};
```
