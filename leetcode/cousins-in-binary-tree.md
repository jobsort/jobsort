# Cousins in Binary Tree Problem & Solution

Given the `root` of a binary tree with unique values and the values of two different nodes of the tree `x` and `y`, return `true` if the nodes corresponding to the values `x` and `y` in the tree are cousins, or `false` otherwise.

Two nodes of a binary tree are cousins if they have the same depth with different parents.

Note that in a binary tree, the `root` node is at the depth `0`, and children of each depth `k` node are at the depth `k + 1`.

See the [cousins in binary tree problem on LeetCode](https://leetcode.com/problems/cousins-in-binary-tree).

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
  bool isCousins(TreeNode* root, int x, int y) {
    metadata left = getMetadata(root, x, 0);
    metadata right = getMetadata(root, y, 0);

    return left.depth == right.depth &&
      left.parent != right.parent;
  }

private:
  struct metadata {
    TreeNode* parent;
    int depth;
  };

  metadata getMetadata(TreeNode* root, int val, int depth) {
    if (root == nullptr) {
      return {nullptr, 0};
    }

    if (root->left && root->left->val == val) {
      return {root, depth + 1};
    }

    if (root->right && root->right->val == val) {
      return {root, depth + 1};
    }

    metadata left = getMetadata(root->left, val, depth + 1);
    if (left.parent) {
      return left;
    } else {
      return getMetadata(root->right, val, depth + 1);
    }
  }
};
```
