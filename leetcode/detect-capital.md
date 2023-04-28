---
name: "Detect Capital"
title: "LeetCode Detect Capital Solution"
description: "Solution for we define the usage of capitals in a word to be right when one of the following cases holds: All letters in this word are capitals, like USA. All letters in this word are not capitals, like leetcode. Only the first letter in this word is capital, like Google. Given a string word, return true if the usage of capitals in it is right."
published: "2021-08-03 PDT"
modified: "2021-08-03 PDT"
---

# Detect Capital Problem & Solution

We define the usage of capitals in a word to be right when one of the following cases holds:

- All letters in this word are capitals, like "USA".
- All letters in this word are not capitals, like "leetcode".
- Only the first letter in this word is capital, like "Google".

Given a string `word`, return true if the usage of capitals in it is right.

See the [detect capital problem on LeetCode](https://leetcode.com/problems/detect-capital).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool detectCapitalUse(string word) {
    bool uppercase = true;
    bool lowercase = true;
    bool sentencecase = true;
    for (int i = 0; i < word.size(); ++i) {
      uppercase &= word[i] >= 'A' && word[i] <= 'Z';
      lowercase &= word[i] >= 'a' && word[i] <= 'z';
      sentencecase &= i == 0
        ? word[i] >= 'A' && word[i] <= 'Z'
        : word[i] >= 'a' && word[i] <= 'z';
    }

    return uppercase || lowercase || sentencecase;
  }
};
```
