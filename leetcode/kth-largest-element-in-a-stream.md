# Kth Largest Element in a Stream Problem & Solution

See the [kth largest element in a stream problem on LeetCode](https://leetcode.com/problems/kth-largest-element-in-a-stream).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class KthLargest {
public:
  KthLargest(int k, vector<int>& nums) {
    this->k = k;
    
    for (int i = 0; i < nums.size(); ++i) { // n
      add(nums[i]);
    }
  }
    
  int add(int val) {
    pq.push(val); // logk
    if (pq.size() > k) {
      pq.pop();
    }

    return pq.top();
  }

private:
  int k;
  priority_queue<int, vector<int>, greater<int>> pq;
};
```
