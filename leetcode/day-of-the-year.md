# Day of the Year Problem & Solution

See the [day of the year problem on LeetCode](https://leetcode.com/problems/day-of-the-year).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("fast-math")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int dayOfYear(string date) {
    int year = stoi(date.substr(0, 4));
    int month = stoi(date.substr(5, 2));
    int day = stoi(date.substr(8, 2));
    vector<int> days{
      31, // January

      // https://en.wikipedia.org/wiki/Leap_year
      year % 4 == 0 && (year % 100 != 0 || (year % 100 == 0 && year % 400 == 0)) ? 29 : 28, // February
      31, // March
      30, // April
      31, // May
      30, // June
      31, // July
      31, // August
      30, // September
      31, // October
      30, // November
      31, // December
    };

    int total = 0;
    for (int i = 0; i < month - 1; ++i) {
      total += days[i];
    }

    total += day;

    return total;
  }
};
```
