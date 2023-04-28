# Diameter of Binary Tree Problem & Solution

Given the `root` of a binary tree, return the length of the diameter of the tree.

The diameter of a binary tree is the length of the longest path between any two nodes in a tree.
This path may or may not pass through the `root`.

The length of a path between two nodes is represented by the number of edges between them.

See the [diameter of binary tree problem on LeetCode](https://leetcode.com/problems/diameter-of-binary-tree).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
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
  int diameterOfBinaryTree(TreeNode* root) {
    int result = 0;
    diameterOfBinaryTree(root, result);

    return result;
  }

private:
  int diameterOfBinaryTree(TreeNode* root, int& diameter) {
    if (root == nullptr) {
      return -1;
    }

    int left = 1 + diameterOfBinaryTree(root->left, diameter);
    int right = 1 + diameterOfBinaryTree(root->right, diameter);
    diameter = max(diameter, left + right);

    return max(left, right);
  }
};
```
