# Univalued Binary Tree Problem & Solution

A binary tree is uni-valued if every node in the tree has the same value.

Given the `root` of a binary tree, return `true` if the given tree is uni-valued, or `false` otherwise.

See the [univalued binary tree problem on LeetCode](https://leetcode.com/problems/univalued-binary-tree).

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
  bool isUnivalTree(TreeNode* root) {
    if (root == nullptr) {
      return true;
    }

    bool ok = true;

    if (root->left) {
      ok &= root->left->val == root->val &&
        isUnivalTree(root->left);
    }

    if (root->right) {
      ok &= root->right->val == root->val &&
        isUnivalTree(root->right);
    }

    return ok;
  }
};
```
