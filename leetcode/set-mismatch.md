# Set Mismatch Problem & Solution

You have a set of integers `s`, which originally contains all the numbers from 1 to `n`.
Unfortunately, due to some error, one of the numbers in `s` got duplicated to another number in the set, which results in repetition of one number and loss of another number.

You are given an integer array `nums` representing the data status of this set after the error.

Find the number that occurs twice and the number that is missing and return them in the form of an array.

See the [set mismatch problem on LeetCode](https://leetcode.com/problems/set-mismatch).

## C++ Solution

The runtime complexity of this algorithm is $O(n)$.

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> findErrorNums(vector<int>& nums) {
    for (int i = 0; i < nums.size(); ++i) {

      // Marks seen elements by making the positions negative.
      nums[abs(nums[i]) - 1] *= -1;
    }

    vector<int> result;
    for (int i = 0; i < nums.size(); ++i) {

      // If `nums[i]` is positive then it's either the duplicated or missing element.
      if (nums[i] > 0) {
        result.push_back(i + 1);
      }
    }

    for (int i = 0; i < nums.size(); ++i) {

      // The duplicated element must be on the first position, so we swap if required.
      if (result[1] == abs(nums[i])) {
        swap(result[0], result[1]);
        break;
      }
    }

    return result;
  }
};
```
