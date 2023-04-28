---
name: "Reverse Linked List"
title: "LeetCode Reverse Linked List Solution"
description: "Solution for the reverse linked list problem from LeetCode."
published: "2021-06-29 PDT"
modified: "2021-06-29 PDT"
---

# Reverse Linked List Problem & Solution

Given the `head` of a singly linked list, reverse the list, and return the reversed list.

See the [reverse linked list problem on LeetCode](https://leetcode.com/problems/reverse-linked-list).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

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
  ListNode* reverseList(ListNode* head) {
    ListNode* prev = nullptr;
    ListNode* cursor = head;

    while (cursor != nullptr) {
      ListNode* tmp = cursor->next;
      cursor->next = prev;
      prev = cursor;

      // Advances cursor to next node.
      cursor = tmp;
    }

    return prev;
  }
};
```
