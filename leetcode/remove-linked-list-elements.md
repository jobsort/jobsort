---
name: "Remove Linked List Elements"
title: "LeetCode Remove Linked List Elements Solution"
description: "Solution for the remove linked list elements problem from LeetCode."
published: "2021-06-27 PDT"
modified: "2021-06-27 PDT"
---

# Remove Linked List Elements Problem & Solution

Given the `head` of a linked list and an integer `val`, remove all the nodes of the linked list that has `Node.val == val`, and return the new `head`.

See the [remove linked list elements problem on LeetCode](https://leetcode.com/problems/remove-linked-list-elements).

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
  ListNode* removeElements(ListNode* head, int val) {
    ListNode dummy(INT_MAX, head);

    ListNode* prev = &dummy;
    ListNode* cursor = head;

    while (cursor != nullptr) {
      if (cursor->val == val) {
        ListNode* tmp = cursor;

        prev->next = cursor->next;

        // Must update head if deleting the first element.
        if (cursor == head) {
          head = cursor->next;
        }

        cursor = cursor->next;
        delete tmp;
      } else {
        prev = cursor;
        cursor = cursor->next;
      }
    }

    return head;
  }
};
```
