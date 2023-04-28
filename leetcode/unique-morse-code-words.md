---
name: "Unique Morse Code Words"
title: "LeetCode Unique Morse Code Words Solution"
description: "Solution for the unique morse code words problem from LeetCode."
published: "2021-12-03 PDT"
modified: "2021-12-03 PDT"
---

# Unique Morse Code Words Problem & Solution

International Morse Code defines a standard encoding where each letter is mapped to a series of dots and dashes, as follows:

- `'a'` maps to `".-"`,
- `'b'` maps to `"-..."`,
- `'c'` maps to `"-.-."`, and so on.

For convenience, the full table for the 26 letters of the English alphabet is given below:

```
[".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."]
```

Given an array of strings `words` where each word can be written as a concatenation of the Morse code of each letter.

For example, `"cab"` can be written as `"-.-..--..."`, which is the concatenation of `"-.-."`, `".-"`, and `"-..."`. We will call such a concatenation the transformation of a word.

Return the number of different transformations among all words we have.

See the [unique morse code words problem on LeetCode](https://leetcode.com/problems/unique-morse-code-words).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int uniqueMorseRepresentations(vector<string>& words) {
    vector<string> morse{".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."};

    unordered_set<string> unique;
    for (int i = 0; i < words.size(); ++i) {
      string s;
      for (int j = 0; j < words[i].size(); ++j) {
        s += morse[words[i][j] - 'a'];
      }

      unique.insert(s);
    }

    return unique.size();
  }
};
```
