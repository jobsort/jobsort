# Delete Node in a Linked List Problem & Solution

Write a function to delete a node in a singly-linked list.
You will not be given access to the head of the list, instead you will be given access to the node to be deleted directly.
It is guaranteed that the node to be deleted is not a tail node in the list.

See the [delete node in a linked list problem on LeetCode](https://leetcode.com/problems/delete-node-in-a-linked-list).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")

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
  void deleteNode(ListNode* node) {
    ListNode* cursor = node->next;

    // Saves the next node onto the node to be deleted; so, the node to be deleted is actually the next node now.
    *node = *cursor;

    // Frees up memory occupied by the next node; otherwise, the next node lives in memory twice.
    // This deletes the initial location of the next node.
    delete cursor;
  }
};
```
