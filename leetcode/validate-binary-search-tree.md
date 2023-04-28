---
name: "Validate Binary Search Tree"
title: "LeetCode Validate Binary Search Tree Solution"
description: "Solution for the validate binary search tree problem from LeetCode."
published: "2023-02-02 PDT"
modified: "2023-02-02 PDT"
---

# Validate Binary Search Tree Problem & Solution

See the [validate binary search tree problem on LeetCode](https://leetcode.com/problems/validate-binary-search-tree).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,max-inline-insns-recursive")
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
  bool isValidBST(TreeNode* root) {
    bool ok = true;
    help(root, ok);

    return ok;
  }

private:
  pair<long, long> help(TreeNode* root, bool& ok) {
    if (root == nullptr || !ok) {
      return {numeric_limits<long>::max(), numeric_limits<long>::min()};
    }

    if (root->left == nullptr && root->right == nullptr) {
      return {root->val, root->val};
    }

    auto left = help(root->left, ok);
    auto right = help(root->right, ok);

    ok &= left.second < root->val && right.first > root->val;

    return {min((long)root->val, min(left.first, right.first)),
      max((long)root->val, max(left.second, right.second))};
  }
};
```
