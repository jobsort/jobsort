# Design Snake Game

See the [design snake game problem on LeetCode](https://leetcode.com/problems/design-snake-game).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class SnakeGame {
public:
  SnakeGame(int width, int height, vector<vector<int>>& food) : _width(width), _height(height), _food(food) {
    _score = 0;
    _snake.push_back({0, 0});
  }
    
  int move(string direction) {
    int ii = direction == "U" ? -1 : (direction == "D" ? +1 : 0);
    int jj = direction == "L" ? -1 : (direction == "R" ? +1 : 0);

    auto head = _snake.front();
    int iii = head[0] + ii;
    int jjj = head[1] + jj;
    if (iii < 0 || iii >= _height ||
        jjj < 0 || jjj >= _width) {
      return -1;
    }

    for (int i = 0; i < _snake.size() - 1; ++i) {
      if (iii == _snake[i][0] && jjj == _snake[i][1]) {
        return -1;
      }
    }

    if (_score < _food.size() && _food[_score][0] == iii && _food[_score][1] == jjj) {
      ++_score;
    } else {
      _snake.pop_back();
    }

    _snake.push_front({iii, jjj});

    return _score;
  }

private:
  int _width;
  int _height;
  int _score;

  vector<vector<int>> _food;  
  deque<vector<int>> _snake;
};
```
