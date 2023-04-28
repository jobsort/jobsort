---
name: "Binary Tree Postorder Traversal"
title: "LeetCode Binary Tree Postorder Traversal Solution"
description: "Solution for the binary tree postorder traversal problem from LeetCode."
published: "2021-06-13 PDT"
modified: "2021-06-13 PDT"
---

# Binary Tree Postorder Traversal Problem & Solution

Given the `root` of a binary tree, return the postorder traversal of its nodes' values.

See the [binary tree postorder traversal problem on LeetCode](https://leetcode.com/problems/binary-tree-postorder-traversal).

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
  vector<int> postorderTraversal(TreeNode* root) {
    vector<int> traversal;

    postorderTraversal(root, traversal);

    return traversal;
  }

private:
  void postorderTraversal(TreeNode* node, vector<int>& traversal) {
    if (node == nullptr) {
      return;
    }

    postorderTraversal(node->left, traversal);
    postorderTraversal(node->right, traversal);
    traversal.push_back(node->val);
  }
};
```
