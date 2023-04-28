---
name: "Maximum Depth of Binary Tree"
title: "LeetCode Maximum Depth of Binary Tree Solution"
description: "Solution for the maximum depth of binary tree problem from LeetCode."
published: "2021-06-04 PDT"
modified: "2021-06-10 PDT"
---

# Maximum Depth of Binary Tree Problem & Solution

Given the `root` of a binary tree, return its maximum depth.
A binary tree's maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

See the [maximum depth of binary tree problem on LeetCode](https://leetcode.com/problems/maximum-depth-of-binary-tree).

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
  int maxDepth(TreeNode* root) {
    if (root == nullptr) {
      return 0;
    }

    return max(maxDepth(root->left), maxDepth(root->right)) + 1;
  }
};
```
