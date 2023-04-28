# Sum of All Odd Length Subarrays Problem & Solution

See the [sum of all odd length subarrays problem on LeetCode](https://leetcode.com/problems/sum-of-all-odd-length-subarrays).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int sumOddLengthSubarrays(vector<int>& arr) {
    int result = 0;

    for (int l = 1; l <= arr.size(); l += 2) {
      int c = 0, sum = 0;
      for (int i = 0; i < arr.size(); ++i) {
        sum += arr[i];
        if (i >= l) {
          sum -= arr[i - l];
        }

        ++c;
        if (c >= l) {
          result += sum;
        }
      }
    }

    return result;
  }
};
```
