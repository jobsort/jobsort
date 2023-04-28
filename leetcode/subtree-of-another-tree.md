# Subtree of Another Tree Problem & Solution

Given the roots of two binary trees `root` and `subRoot`, return true if there is a subtree of `root` with the same structure and node values of `subRoot` and false otherwise.

A subtree of a binary tree tree is a tree that consists of a node in tree and all of this node's descendants.
The tree tree could also be considered as a subtree of itself.

See the [subtree of another tree problem on LeetCode](https://leetcode.com/problems/subtree-of-another-tree).

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
  bool isSubtree(TreeNode* root, TreeNode* subRoot) {
    if (root == nullptr || subRoot == nullptr) {
      return false;
    }

    bool result = false;
    if (root->val == subRoot->val) {
      result = testSubtree(root, subRoot);
    }

    return result ||
      isSubtree(root->left, subRoot) ||
      isSubtree(root->right, subRoot);
  }

private:
  bool testSubtree(TreeNode* root, TreeNode* subRoot) {
    if (root == nullptr && subRoot == nullptr) {
      return true;
    }

    if ((root && !subRoot) || (!root && subRoot)) {
      return false;
    }

    return root->val == subRoot->val &&
      testSubtree(root->left, subRoot->left) &&
      testSubtree(root->right, subRoot->right);
  }
};
```
