---
name: "Generate Parentheses"
title: "LeetCode Generate Parentheses Solution"
description: "Solution for the generate parentheses problem from LeetCode."
published: "2022-09-13 PDT"
modified: "2022-09-13 PDT"
---

# Generate Parentheses Problem & Solution

See the [generate parentheses problem on LeetCode](https://leetcode.com/problems/generate-parentheses).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

using namespace std;

class Solution {
public:
  vector<string> generateParenthesis(int n) {
    vector<string> result;

    help(0, "", n, result);

    return result;
  }

private:
  void help(int sum, string str, int n, vector<string>& result) {
    if (str.size() > n * 2) {
      return;
    }

    if (sum == 0 && str.size() == n * 2) {
      result.push_back(str);
      return;
    }

    if (sum < n) {
      help(sum + 1, str + '(', n, result);
    }

    if (sum > 0) {
      help(sum - 1, str + ')', n, result);
    }
  }
};
```
