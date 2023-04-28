# Merge Two Sorted Lists Problem & Solution

Merge two sorted linked lists and return it as a sorted list. The list should be made by splicing together the nodes of the first two lists.

See the [merge two sorted lists problem on LeetCode](https://leetcode.com/problems/merge-two-sorted-lists).

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
  ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
    if (l1 == nullptr) {
      return l2;
    }

    if (l2 == nullptr) {
      return l1;
    }

    ListNode* root = new ListNode();
    ListNode* cursor = root;

    while (l1 != nullptr && l2 != nullptr) {
      if (l1->val > l2->val) {
        cursor->next = l2;
        l2 = l2->next;
        cursor = cursor->next;
      } else {
        cursor->next = l1;
        l1 = l1->next;
        cursor = cursor->next;
      }
    }

    if (l1 != nullptr) {
      cursor->next = l1;
    }

    if (l2 != nullptr) {
      cursor->next = l2;
    }

    cursor = root->next;
    delete root;

    return cursor;
  }
};
```
