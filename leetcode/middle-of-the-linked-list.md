# Middle of the Linked List Problem & Solution

Given the `head` of a singly linked list, return the middle node of the linked list.

If there are two middle nodes, return the second middle node.

See the [middle of the linked list problem on LeetCode](https://leetcode.com/problems/middle-of-the-linked-list).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

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
  ListNode* middleNode(ListNode* head) {
    int len = 0;
    ListNode* cursor = head;
    while (cursor != nullptr) {
      cursor = cursor->next;
      ++len;
    }

    len /= 2;
    cursor = head;
    while (len-- > 0) {
      cursor = cursor->next;
    }

    return cursor;
  }
};
```
