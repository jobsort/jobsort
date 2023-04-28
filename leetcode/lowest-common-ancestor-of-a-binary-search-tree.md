---
name: "Lowest Common Ancestor of a Binary Search Tree"
title: "LeetCode Lowest Common Ancestor of a Binary Search Tree Solution"
description: "Solution for the lowest common ancestor of a binary search tree problem from LeetCode."
published: "2021-07-15 PDT"
modified: "2021-07-15 PDT"
---

# Lowest Common Ancestor of a Binary Search Tree Problem & Solution

Given a binary search tree (BST), find the lowest common ancestor (LCA) of two given nodes in the BST.
According to the definition of LCA on Wikipedia: "The lowest common ancestor is defined between two nodes p and q as the lowest node in T that has both p and q as descendants (where we allow a node to be a descendant of itself)."

See the [lowest common ancestor of a binary search tree problem on LeetCode](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("max-inline-insns-recursive-auto")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

/**
 * struct TreeNode {
 *   int val;
 *   TreeNode *left;
 *   TreeNode *right;
 *   TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
  TreeNode* lowestCommonAncestor(TreeNode* root, TreeNode* p, TreeNode* q) {
    if (p->val < root->val && q->val < root->val) {
      return lowestCommonAncestor(root->left, p, q);
    } else if (p->val > root->val && q->val > root->val) {
      return lowestCommonAncestor(root->right, p, q);
    } else {
      return root;
    }
  }
};
```
