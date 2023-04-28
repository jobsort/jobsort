---
name: "Search in a Binary Search Tree"
title: "LeetCode Search in a Binary Search Tree Solution"
description: "Solution for you are given the root of a binary search tree (BST) and an integer val. Find the node in the BST that the node's value equals val and return the subtree rooted with that node. If such a node does not exist, return null."
published: "2021-08-22 PDT"
modified: "2021-08-22 PDT"
---

# Search in a Binary Search Tree Problem & Solution

You are given the `root` of a binary search tree (BST) and an integer `val`.

Find the node in the BST that the node's value equals `val` and return the subtree rooted with that node.
If such a node does not exist, return null.

See the [search in a binary search tree problem on LeetCode](https://leetcode.com/problems/search-in-a-binary-search-tree).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("max-inline-insns-recursive-auto")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

/**
 * struct TreeNode {
 *   int val;
 *   TreeNode *left;
 *   TreeNode *right;
 *   TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *   TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *   TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
  TreeNode* searchBST(TreeNode* root, int val) {
    if (root == nullptr) {
      return nullptr;
    }

    if (root->val == val) {
      return root;
    }

    if (root->val > val) {

      // This is tail recursion, so as good as iterative approach.
      return searchBST(root->left, val);
    } else {
      return searchBST(root->right, val);
    }
  }
};
```
