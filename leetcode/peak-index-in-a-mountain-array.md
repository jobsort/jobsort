# Peak Index in a Mountain Array Problem & Solution

Let's call an array `arr` a mountain if the following properties hold:

- `arr.length >= 3`
- There exists some `i` with `0 < i < arr.length - 1` such that:
  - `arr[0] < arr[1] < ... arr[i-1] < arr[i]`
  - `arr[i] > arr[i+1] > ... > arr[arr.length - 1]`

Given an integer array `arr` that is guaranteed to be a mountain, return any `i` such that `arr[0] < arr[1] < ... arr[i - 1] < arr[i] > arr[i + 1] > ... > arr[arr.length - 1]`.

See the [peak index in a mountain array problem on LeetCode](https://leetcode.com/problems/peak-index-in-a-mountain-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("max-inline-insns-recursive-auto")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int peakIndexInMountainArray(vector<int>& arr) {
    return bs(arr, 0, arr.size() - 1);
  }

private:
  int bs(vector<int> &arr, int low, int high) {
    int mid = low + (high - low) / 2;

    if (arr[mid] > arr[mid - 1] &&
        arr[mid] > arr[mid + 1]) {
      return mid;
    }

    if (arr[mid] > arr[mid - 1]) {
      return bs(arr, mid + 1, high);
    } else {
      return bs(arr, low, high - 1);
    }
  }
};
```
