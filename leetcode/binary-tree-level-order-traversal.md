---
name: "Binary Tree Level Order Traversal"
title: "LeetCode Binary Tree Level Order Traversal Solution"
description: "Solution for the binary tree level order traversal problem from LeetCode."
published: "2023-02-03 PDT"
modified: "2023-02-03 PDT"
---

# Binary Tree Level Order Traversal Problem & Solution

See the [binary tree level order traversal problem on LeetCode](https://leetcode.com/problems/binary-tree-level-order-traversal).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

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
  vector<vector<int>> levelOrder(TreeNode* root) {
    vector<vector<int>> results;

    help(root, results, 1);

    return results;
  }

private:
  void help(TreeNode* root, vector<vector<int>>& results, int level) {
    if (root == nullptr) {
      return;
    }

    if (results.size() < level) {
      results.push_back({});
    }

    results[level - 1].push_back(root->val);

    help(root->left, results, level + 1);
    help(root->right, results, level + 1);
  }
};
```
