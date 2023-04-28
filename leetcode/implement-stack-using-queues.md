---
name: "Implement Stack using Queues"
title: "LeetCode Implement Stack using Queues Solution"
description: "Solution for the implement stack using queues problem from LeetCode."
published: "2023-02-05 PDT"
modified: "2023-02-05 PDT"
---

# Implement Stack using Queues Problem & Solution

See the [implement stack using queues problem on LeetCode](https://leetcode.com/problems/implement-stack-using-queues).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class MyStack {
public:
  MyStack() {
    // noop
  }

  void push(int x) {
    q.push(x);
  }

  int pop() {
    queue<int> w;

    while (!q.empty()) {
      int top = q.front();
      q.pop();

      w.push(top);
    }

    while (w.size() > 1) {
      int top = w.front();
      w.pop();

      q.push(top);
    }

    return w.front();
  }

  int top() {
    return q.back();
  }

  bool empty() {
    return q.empty();
  }

private:
  queue<int> q;
};
```
