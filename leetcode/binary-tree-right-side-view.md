---
name: "Binary Tree Right Side View"
title: "LeetCode Binary Tree Right Side View Solution"
description: "Solution for the binary tree right side view problem from LeetCode."
published: "2023-02-04 PDT"
modified: "2023-02-04 PDT"
---

# Binary Tree Right Side View Problem & Solution

See the [binary tree right side view problem on LeetCode](https://leetcode.com/problems/binary-tree-right-side-view).

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
  vector<int> rightSideView(TreeNode* root) {
    vector<int> results;
    help(root, results, 1);

    return results;
  }

private:
  void help(TreeNode* root, vector<int>& results, int level) {
    if (root == nullptr) {
      return;
    }

    if (results.size() < level) {
      results.push_back(root->val);
    } else {
      results[level - 1] = root->val;
    }

    help(root->left, results, level + 1);
    help(root->right, results, level + 1);
  }
};
```
