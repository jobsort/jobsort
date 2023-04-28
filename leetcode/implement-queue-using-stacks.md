---
name: "Implement Queue using Stacks"
title: "LeetCode Implement Queue using Stacks Solution"
description: "Solution for the implement queue using stacks problem from LeetCode."
published: "2023-02-06 PDT"
modified: "2023-02-06 PDT"
---

# Implement Queue using Stacks Problem & Solution

See the [implement queue using stacks problem on LeetCode](https://leetcode.com/problems/implement-queue-using-stacks).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class MyQueue {
public:
  MyQueue() {
    // noop
  }

  void push(int x) {
    s.push(x);
  }

  int pop() {
    stack<int> p;
    while (!s.empty()) {
      int top = s.top();
      s.pop();

      p.push(top);
    }

    int result = p.top();
    p.pop();

    while (!p.empty()) {
      int top = p.top();
      p.pop();

      s.push(top);
    }

    return result;
  }

  int peek() {
    stack<int> p;
    while (!s.empty()) {
      int top = s.top();
      s.pop();

      p.push(top);
    }

    int result = p.top();
    // p.pop();

    while (!p.empty()) {
      int top = p.top();
      p.pop();

      s.push(top);
    }

    return result;
  }

  bool empty() {
    return s.empty();
  }

private:
  stack<int> s;
};
```
