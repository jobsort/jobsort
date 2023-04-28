# Binary Tree Tilt Problem & Solution

Given the `root` of a binary tree, return the sum of every tree node's tilt.

The tilt of a tree node is the absolute difference between the sum of all left subtree node values and all right subtree node values.
If a node does not have a left child, then the sum of the left subtree node values is treated as 0.
The rule is similar if there the node does not have a right child.

See the [binary tree tilt problem on LeetCode](https://leetcode.com/problems/binary-tree-tilt).

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
  int findTilt(TreeNode* root) {
    int result = 0;
    findTilt(root, result);

    return result;
  }

private:
  int findTilt(TreeNode* root, int& sum) {
    if (root == nullptr) {
      return 0;
    }

    if (root->left == nullptr && root->right == nullptr) {
      return root->val;
    }

    int left = findTilt(root->left, sum);
    int right = findTilt(root->right, sum);

    sum += abs(left - right);

    return left + right + root->val;
  }
};
```
