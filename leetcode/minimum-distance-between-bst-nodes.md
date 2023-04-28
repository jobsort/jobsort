# Minimum Distance Between BST Nodes Problem & Solution

Given the `root` of a Binary Search Tree (BST), return the minimum difference between the values of any two different nodes in the tree.

See the [minimum distance between BST nodes problem on LeetCode](https://leetcode.com/problems/minimum-distance-between-bst-nodes).

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
  int minDiffInBST(TreeNode* root) {
    TreeNode* prev = nullptr;
    int diff = numeric_limits<int>::max();

    minDiffInBST(root, &prev, diff);

    return diff;
  }

private:
  void minDiffInBST(TreeNode* root, TreeNode** prev, int& diff) {
    if (root == nullptr) {
      return;
    }

    minDiffInBST(root->left, prev, diff);
    if (*prev != nullptr) {
      diff = min(diff, root->val - (*prev)->val);
    }

    *prev = root;
    minDiffInBST(root->right, prev, diff);
  }
};
```
