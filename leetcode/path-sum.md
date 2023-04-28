---
name: "Path Sum"
title: "LeetCode Path Sum Solution"
description: "Solution for the path sum problem from LeetCode."
published: "2021-06-05 PDT"
modified: "2021-06-09 PDT"
---

# Path Sum Problem & Solution

Given the `root` of a binary tree and an integer `targetSum`, return `true` if the tree has a root-to-leaf path such that adding up all the values along the path equals `targetSum`.
A leaf is a node with no children.

See the [path sum problem on LeetCode](https://leetcode.com/problems/path-sum).

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
  bool hasPathSum(TreeNode* root, int targetSum) {
    if (root == nullptr) {
      return false;
    }

    if (root->left == nullptr && root->right == nullptr) {
      return targetSum == root->val;
    }

    return hasPathSum(root->left, targetSum - root->val) ||
      hasPathSum(root->right, targetSum - root->val);
  }
};
```
