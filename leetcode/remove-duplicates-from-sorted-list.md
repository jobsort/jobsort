---
name: "Remove Duplicates from Sorted List"
title: "LeetCode Remove Duplicates from Sorted List Solution"
description: "Solution for the remove duplicates from sorted list problem from LeetCode."
published: "2021-06-02 PDT"
modified: "2021-06-09 PDT"
---

# Remove Duplicates from Sorted List Problem & Solution

Given the `head` of a sorted linked list, delete all duplicates such that each element appears only once.
Return the linked list sorted as well.

See the [remove duplicates from sorted list problem on LeetCode](https://leetcode.com/problems/remove-duplicates-from-sorted-list).

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
  ListNode* deleteDuplicates(ListNode* head) {
    ListNode* cursor = head;
    while (cursor != nullptr && cursor->next != nullptr) {
      while (cursor != nullptr && cursor->next != nullptr &&
             cursor->val == cursor->next->val) {
        ListNode* tmp = cursor->next;

        cursor->next = tmp->next;
        delete tmp;
      }

      cursor = cursor->next;
    }

    return head;
  }
};
```
