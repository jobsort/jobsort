---
name: "Binary Tree Paths"
title: "LeetCode Binary Tree Paths Solution"
description: "Solution for the binary tree paths problem from LeetCode."
published: "2021-07-14 PDT"
modified: "2021-07-14 PDT"
---

# Binary Tree Paths Problem & Solution

Given the `root` of a binary tree, return all root-to-leaf paths in any order.
A leaf is a node with no children.

See the [binary tree paths problem on LeetCode](https://leetcode.com/problems/binary-tree-paths).

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
  vector<string> binaryTreePaths(TreeNode* root) {
    vector<string> results;

    binaryTreePaths(root, "", results);

    return results;
  }

private:
  void binaryTreePaths(TreeNode* root, string result, vector<string>& results) {
    if (root == nullptr) {
      return;
    }

    if (root->left == nullptr && root->right == nullptr) {
      result += to_string(root->val);
      results.push_back(result);
    }

    string tmp = result + to_string(root->val) + "->";

    binaryTreePaths(root->left, tmp, results);
    binaryTreePaths(root->right, tmp, results);
  }
};
```
