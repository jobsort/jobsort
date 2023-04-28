# Linked List Cycle Problem & Solution

Given `head`, the head of a linked list, determine if the linked list has a cycle in it.
There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the next pointer.
Internally, pos is used to denote the index of the node that tail's next pointer is connected to.
Note that pos is not passed as a parameter.
Return true if there is a cycle in the linked list.
Otherwise, return false.

See the [linked list cycle problem on LeetCode](https://leetcode.com/problems/linked-list-cycle).

## C++ Solution

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
  bool hasCycle(ListNode *head) {
    if (head == nullptr || head->next == nullptr) {
      return false;
    }

    ListNode* slow = head;
    ListNode* fast = head->next;

    while (slow != nullptr &&
           fast != nullptr && fast->next != nullptr &&
           slow != fast) {
      slow = slow->next;
      fast = fast->next->next;
    }

    return slow == fast;
  }
};
```
