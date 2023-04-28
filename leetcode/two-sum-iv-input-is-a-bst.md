---
name: "Two Sum IV - Input is a BST"
title: "LeetCode Two Sum IV - Input is a BST Solution"
description: "Solution for given the root of a Binary Search Tree and a target number k, return true if there exist two elements in the BST such that their sum is equal to the given target."
published: "2021-09-07 PDT"
modified: "2021-09-07 PDT"
---

# Two Sum IV - Input is a BST Problem & Solution

Given the `root` of a Binary Search Tree and a target number `k`, return true if there exist two elements in the BST such that their sum is equal to the given target.

See the [two sum iv input is a BST problem on LeetCode](https://leetcode.com/problems/two-sum-iv-input-is-a-bst).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
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
  bool findTarget(TreeNode* root, int k) {
    return findTarget(root, root, k);
  }

private:
  bool findTarget(TreeNode* root, TreeNode* node, int k) {
    if (node == nullptr) {
      return false;
    }

    return findNode(root, node, k - node->val) ||
      findTarget(root, node->left, k) ||
      findTarget(root, node->right, k);
  }

  bool findNode(TreeNode* root, TreeNode* node, int k) {
    while (root != nullptr) {
      if (root != node &&
          root->val == k) {
        return true;
      }

      if (k < root->val) {
        root = root->left;
      } else {
        root = root->right;
      }
    }

    return false;
  }
};
```
