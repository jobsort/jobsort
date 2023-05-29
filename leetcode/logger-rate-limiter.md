# Logger Rate Limiter Problem & Solution

See the [logger rate limiter problem on LeetCode](https://leetcode.com/problems/logger-rate-limiter).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Logger {
public:
  Logger() {
    // noop
  }
    
  bool shouldPrintMessage(int timestamp, string message) {
    if (hash.find(message) == hash.end()) {
      hash[message] = timestamp;

      return true;
    } else {
      bool result = timestamp >= hash[message] + delay;
      if (result) {
        hash[message] = timestamp;
      }

      return result;
    }
    
  }

private:
  const int delay = 10;

  unordered_map<string, int> hash;  
};
```
