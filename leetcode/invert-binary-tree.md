---
name: "Invert Binary Tree"
title: "LeetCode Invert Binary Tree Solution"
description: "Solution for the invert binary tree problem from LeetCode."
published: "2021-07-15 PDT"
modified: "2021-07-15 PDT"
---

# Invert Binary Tree Problem & Solution

Given the `root` of a binary tree, invert the tree, and return its `root`.

See the [invert binary tree problem on LeetCode](https://leetcode.com/problems/invert-binary-tree).

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
 *   TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *   TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *   TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
  TreeNode* invertTree(TreeNode* root) {
    if (root == nullptr) {
      return nullptr;
    }

    swap(root->left, root->right);
    invertTree(root->left);
    invertTree(root->right);

    return root;
  }
};
```
