# Asteroid Collision Problem & Solution

See the [asteroid collision problem on LeetCode](https://leetcode.com/problems/asteroid-collision).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> asteroidCollision(vector<int>& asteroids) {
    int i = -1;
    for (int j = 0; j < asteroids.size(); ++j) {
      if (asteroids[j] > 0) {
        asteroids[++i] = asteroids[j];
      } else {
        while (i >= 0 && asteroids[i] > 0 && asteroids[i] < abs(asteroids[j])) {
          asteroids[i--] = asteroids[j];
        }

        if (i >= 0 && asteroids[i] == abs(asteroids[j])) {
          --i;

          continue;
        }

        if (i == -1 || i >= 0 && asteroids[i] < 0) {
          asteroids[++i] = asteroids[j];
        }
      }
    }

    asteroids.erase(asteroids.begin() + i + 1, asteroids.end());

    return asteroids;
  }
};
```
