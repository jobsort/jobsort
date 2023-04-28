# Convert the Temperature Problem & Solution

See the [convert the temperature problem on LeetCode](https://leetcode.com/problems/convert-the-temperature).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<double> convertTemperature(double celsius) {
    double kelvin = celsius + 273.15;
    double fahrenheit = celsius * 1.8 + 32;

    return {kelvin, fahrenheit};
  }
};
```
