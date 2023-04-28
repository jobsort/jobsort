# Day of the Week Problem & Solution

See the [day of the week problem on LeetCode](https://leetcode.com/problems/day-of-the-week).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string dayOfTheWeek(int day, int month, int year) {
    tm tm{};
    tm.tm_year = year - 1900;
    tm.tm_mon = month - 1;
    tm.tm_mday = day;

    mktime(&tm);

    ostringstream oss;
    oss << put_time(&tm, "%A");

    return oss.str();
  }
};
```
