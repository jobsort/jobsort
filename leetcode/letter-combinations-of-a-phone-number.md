# Letter Combinations of a Phone Number Problem & Solution

See the [letter combinations of a phone number problem on LeetCode](https://leetcode.com/problems/letter-combinations-of-a-phone-number).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("max-inline-insns-recursive,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);cout.setstate(ios_base::failbit);return 0;}();

class Solution {
public:
  vector<string> letterCombinations(string digits) {
    if (digits == "") {
      return {};
    }

    unordered_map<char, vector<char>> const nums{
      {'2', {'a', 'b', 'c'}},
      {'3', {'d', 'e', 'f'}},
      {'4', {'g', 'h', 'i'}},
      {'5', {'j', 'k', 'l'}},
      {'6', {'m', 'n', 'o'}},
      {'7', {'p', 'q', 'r', 's'}},
      {'8', {'t', 'u', 'v',}},
      {'9', {'w', 'x', 'y', 'z'}}
    };
    vector<string> results;
    string result;

    letterCombinations(digits, 0, result, results, nums);

    return results;
  }

private:
  void letterCombinations(string digits, int i, string& result, vector<string>& results, const unordered_map<char, vector<char>>& nums) {
    if (i == digits.size()) {
      results.push_back(result);
      return;
    }

    for (int j = 0; j < nums.at(digits[i]).size(); ++j) {
      result.push_back(nums.at(digits[i])[j]);
      letterCombinations(digits, i + 1, result, results, nums);
      result.pop_back();
    }
  }
};
```
