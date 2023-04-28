---
name: "Binary Tree Preorder Traversal"
title: "LeetCode Binary Tree Preorder Traversal Solution"
description: "Solution for the binary tree preorder traversal problem from LeetCode."
published: "2021-06-12 PDT"
modified: "2021-06-18 PDT"
---

# Binary Tree Preorder Traversal Problem & Solution

Given the `root` of a binary tree, return the preorder traversal of its nodes' values.

See the [binary tree preorder traversal problem on LeetCode](https://leetcode.com/problems/binary-tree-preorder-traversal).

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
  vector<int> preorderTraversal(TreeNode* root) {
    vector<int> traversal;

    preorderTraversal(root, traversal);

    return traversal;
  }

private:
  void preorderTraversal(TreeNode* node, vector<int>& traversal) {
    if (node == nullptr) {
      return;
    }

    traversal.push_back(node->val);
    preorderTraversal(node->left, traversal);
    preorderTraversal(node->right, traversal);
  }
};
```
