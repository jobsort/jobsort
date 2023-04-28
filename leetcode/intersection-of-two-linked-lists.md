---
name: "Intersection of Two Linked Lists"
title: "LeetCode Intersection of Two Linked Lists Solution"
description: "Solution for the intersection of two linked lists problem from LeetCode."
published: "2021-06-23 PDT"
modified: "2021-06-23 PDT"
---

# Intersection of Two Linked Lists Problem & Solution

Given the heads of two singly linked-lists `headA` and `headB`, return the node at which the two lists intersect.
If the two linked lists have no intersection at all, return null.

See the [intersection of two linked lists problem on LeetCode](https://leetcode.com/problems/intersection-of-two-linked-lists).

## C++ Solution

The runtime complexity of the algorithm is $O(n + m)$.

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

/**
 * struct ListNode {
 *   int val;
 *   ListNode *next;
 *   ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
  ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
    int lenA = 0;
    ListNode* cursorA = headA;
    while (cursorA != nullptr) {
      cursorA = cursorA->next;
      ++lenA;
    }

    int lenB = 0;
    ListNode* cursorB = headB;
    while (cursorB != nullptr) {
      cursorB = cursorB->next;
      ++lenB;
    }

    while (lenA > lenB) {
      headA = headA->next;
      --lenA;
    }

    while (lenB > lenA) {
      headB = headB->next;
      --lenB;
    }

    // At this step, `lenA == lenB`.
    while (lenA > 0) {
      if (headA == headB) {
        return headA;
      }

      headA = headA->next;
      headB = headB->next;
      --lenA;
    }

    return nullptr;
  }
};
```
