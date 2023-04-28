---
name: "Symmetric Tree"
title: "LeetCode Symmetric Tree Solution"
description: "Solution for the symmetric tree problem from LeetCode."
published: "2021-06-03 PDT"
modified: "2021-06-09 PDT"
---

# Symmetric Tree Problem & Solution

Given the `root` of a binary tree, check whether it is a mirror of itself (i.e., symmetric around its center).

See the [symmetric tree problem on LeetCode](https://leetcode.com/problems/symmetric-tree).

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
  bool isSymmetric(TreeNode* root) {
    if (root == nullptr) {
      return true;
    }

    return isSymmetric(root->left, root->right);
  }

private:
  bool isSymmetric(TreeNode* left, TreeNode* right) {
    if ((left != nullptr && right == nullptr) ||
        (left == nullptr && right != nullptr)) {
      return false;
    }

    if (left == nullptr && right == nullptr) {
      return true;
    }

    return left->val == right->val &&
      isSymmetric(left->left, right->right) &&
      isSymmetric(left->right, right->left);
  }
};
```
