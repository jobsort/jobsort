---
name: "Reorder List"
title: "LeetCode Reorder List Solution"
description: "Solution for the reorder list problem from LeetCode."
published: "2023-02-24 PDT"
modified: "2023-02-24 PDT"
---

# Reorder List Problem & Solution

See the [reorder list problem on LeetCode](https://leetcode.com/problems/reorder-list).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

/**
 * struct ListNode {
 *   int val;
 *   ListNode *next;
 *   ListNode() : val(0), next(nullptr) {}
 *   ListNode(int x) : val(x), next(nullptr) {}
 *   ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
  void reorderList(ListNode* head) {
    stack<ListNode*> st;

    ListNode *cursor = head;
    while (cursor != nullptr) {
      st.push(cursor);
      cursor = cursor->next;
    }

    cursor = head;

    int half = st.size() / 2;
    for (int i = 0; i < half; ++i) {
      ListNode *top = st.top();
      st.pop();

      ListNode *next = cursor->next;
      cursor->next = top;
      top->next = next;

      cursor = next;
    }

    cursor->next = nullptr;
  }
};
```
