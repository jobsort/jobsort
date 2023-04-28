---
name: "Print in Order"
title: "LeetCode Print in Order Solution"
description: "Solution for the print in order problem from LeetCode."
published: "2022-03-29 PDT"
modified: "2022-03-29 PDT"
---

# Print in Order Problem & Solution

See the [print in order problem on LeetCode](https://leetcode.com/problems/print-in-order).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Foo {
public:
  Foo() {
    mtx2.lock();
    mtx3.lock();
  }

  void first(function<void()> printFirst) {
    printFirst();
    mtx2.unlock();
  }

  void second(function<void()> printSecond) {
    mtx2.lock();
    printSecond();
    mtx2.unlock();
    mtx3.unlock();
  }

  void third(function<void()> printThird) {
    mtx3.lock();
    printThird();
    mtx3.unlock();
  }

private:
  mutex mtx2;
  mutex mtx3;
};
```
