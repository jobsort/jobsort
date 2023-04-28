# Minimum Depth of Binary Tree Problem & Solution

Given a binary tree, find its minimum depth.
The minimum depth is the number of nodes along the shortest path from the root node down to the nearest leaf node.
A leaf is a node with no children.

See the [minimum depth of binary tree problem on LeetCode](https://leetcode.com/problems/minimum-depth-of-binary-tree).

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
  int minDepth(TreeNode* root) {
    if (root == nullptr) {
      return 0;
    }

    int result = INT_MAX;

    minDepth(root, 0, result);

    return result;
  }

private:
  void minDepth(TreeNode* root, int depth, int& result) {
    if (root == nullptr) {
      return;
    }

    if (root->left == nullptr && root->right == nullptr) {
      result = min(result, depth + 1);
    }

    minDepth(root->left, depth + 1, result);
    minDepth(root->right, depth + 1, result);
  }
};
```
