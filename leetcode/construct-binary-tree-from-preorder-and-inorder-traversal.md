---
name: "Construct Binary Tree from Preorder and Inorder Traversal"
title: "LeetCode Construct Binary Tree from Preorder and Inorder Traversal Solution"
description: "Solution for the construct binary tree from preorder and inorder traversal problem from LeetCode."
published: "2023-03-20 PDT"
modified: "2023-03-20 PDT"
---

# Construct Binary Tree from Preorder and Inorder Traversal Problem & Solution

See the [construct binary tree from preorder and inorder traversal problem on LeetCode](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC taget("avx,avx2,fma")

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
  TreeNode* buildTree(vector<int>& preorder, vector<int>& inorder) {
    int k = 0;
    return help(preorder, inorder, k, 0, preorder.size() - 1);
  }

private:
  TreeNode* help(vector<int>& preorder, vector<int>& inorder, int& k, int low, int high) {
    if (low > high) {
      return nullptr;
    }

    auto node = new TreeNode(preorder[k++]);

    int i;
    for (i = low; i <= high; ++i) {
      if (inorder[i] == node->val) {
        break;
      }
    }

    node->left = help(preorder, inorder, k, low, i - 1);
    node->right = help(preorder, inorder, k, i + 1, high);

    return node;
  }
};
```
