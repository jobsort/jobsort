# Duplicate Zeros Problem & Solution

See the [duplicate zeros problem on LeetCode](https://leetcode.com/problems/duplicate-zeros).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  void duplicateZeros(vector<int>& arr) {
    int count = 0;
    int size = arr.size() - 1;
    for (int i = 0; i <= size - count; ++i) {
      if (arr[i] == 0) {
        if (i == size - count) {
          arr[size--] = 0;
          break;
        }

        ++count;
      }
    }

    for (int i = size - count; i >= 0; —i) {
      if (arr[i] == 0) {
        arr[i + count--] = 0;
        arr[i + count] = 0;
      } else {
        arr[i + count] = arr[i];
      }
    }
  }
};
```
