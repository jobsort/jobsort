---
name: "Binary Tree Inorder Traversal"
title: "LeetCode Binary Tree Inorder Traversal Solution"
description: "Solution for the binary tree inorder traversal problem from LeetCode."
published: "2021-06-03 PDT"
modified: "2021-06-10 PDT"
---

# Binary Tree Inorder Traversal Problem & Solution

Given the `root` of a binary tree, return the inorder traversal of its nodes' values.

See the [binary tree inorder traversal problem on LeetCode](https://leetcode.com/problems/binary-tree-inorder-traversal).

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
  vector<int> inorderTraversal(TreeNode* root) {
    vector<int> path;

    inorderTraversal(root, path);

    return path;
  }

private:
  void inorderTraversal(TreeNode* node, vector<int>& path) {
    if (node == nullptr) {
      return;
    }

    inorderTraversal(node->left, path);
    path.push_back(node->val);
    inorderTraversal(node->right, path);
  }
};
```
