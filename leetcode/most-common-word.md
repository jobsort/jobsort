# Most Common Word Problem & Solution

See the [most common word problem on LeetCode](https://leetcode.com/problems/most-common-word).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string mostCommonWord(string paragraph, vector<string>& banned) {
    unordered_map<string, int> freq;
    set<string> ban(banned.begin(), banned.end());

    int highest = 0;
    string result;
    string s;
    for (int i = 0; i <= paragraph.size(); ++i) {
      char c = paragraph[i];

      if (c == ' ' || c == '!' || c == '?' || c == '\'' || c == ',' || c == ';' || c == '.' || c == '"' || i == paragraph.size()) {
        if (s!= "" &&
            ban.find(s) == ban.end() &&
            ++freq[s] > highest) {
          highest = freq[s];
          result = s;
        }

        s = "";
      } else {
        s += tolower(c);
      }
    }

    return result;
  }
};
```
