# Balanced Binary Tree Problem & Solution

Given a binary tree, determine if it is height-balanced.
For this problem, a height-balanced binary tree is defined as: a binary tree in which the left and right subtrees of every node differ in height by no more than 1.

See the [balanced binary tree problem on LeetCode](https://leetcode.com/problems/balanced-binary-tree).

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
  bool isBalanced(TreeNode* root) {
    bool ok = true;

    isBalanced(root, ok);

    return ok;
  }

private:
  int isBalanced(TreeNode* root, bool& ok) {
    if (root == nullptr) {
      return 0;
    }

    int left = isBalanced(root->left, ok);
    int right = isBalanced(root->right, ok);

    if (abs(left - right) > 1) {
      ok = false;
    }

    return max(left, right) + 1;
  }
};
```
