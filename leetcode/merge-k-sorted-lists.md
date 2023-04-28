# Merge K Sorted Lists Problem & Solution

See the [merge k sorted lists problem on LeetCode](https://leetcode.com/problems/merge-k-sorted-lists).

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
  ListNode* mergeKLists(vector<ListNode*>& lists) {
    auto compare = [](auto *a, auto *b){ return a->val > b->val; };
    priority_queue<ListNode*, vector<ListNode*>, decltype(compare)> pq(compare);

    for (int i = 0; i < lists.size(); ++i) {
      if (lists[i] != nullptr) {
        pq.push(lists[i]);
      }
    }

    ListNode *head = nullptr, *tail = nullptr;
    while (!pq.empty()) {
      ListNode *top = pq.top();
      pq.pop();

      if (head == nullptr) {
        head = tail = top;
      } else {
        tail->next = top;
        tail = top;
      }

      if (top->next != nullptr) {
        pq.push(top->next);
      }
    }

    return head;
  }
};
```
