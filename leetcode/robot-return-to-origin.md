# Robot Return to Origin Problem & Solution

There is a robot starting at the position (0, 0), the origin, on a 2D plane. Given a sequence of its moves, judge if this robot ends up at (0, 0) after it completes its moves.

You are given a string `moves` that represents the move sequence of the robot where `moves[i]` represents its `i`th move. Valid moves are `'R'` (right), `'L'` (left), `'U'` (up), and `'D'` (down).

Return true if the robot returns to the origin after it finishes all of its moves, or false otherwise.

Note: The way that the robot is "facing" is irrelevant. `'R'` will always make the robot move to the right once, `'L'` will always make it move left, etc. Also, assume that the magnitude of the robot's movement is the same for each move.

See the [robot return to origin problem on LeetCode](https://leetcode.com/problems/robot-return-to-origin).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool judgeCircle(string moves) {
    int x = 0;
    int y = 0;
    for (int i = 0; i < moves.size(); ++i) {
      switch (moves[i]) {
        case 'U':
          --y;
          break;
        case 'D':
          ++y;
          break;
        case 'L':
          --x;
          break;
        case 'R':
          ++x;
          break;
      }
    }

    return x == 0 && y == 0;
  }
};
```
