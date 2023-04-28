# Increasing Order Search Tree Problem & Solution

Given the `root` of a binary search tree, rearrange the tree in in-order so that the leftmost node in the tree is now the root of the tree, and every node has no left child and only one right child.

See the [increasing order search tree problem on LeetCode](https://leetcode.com/problems/increasing-order-search-tree).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("max-inline-insns-recursive-auto")
#pragma GCC target("avx,avx2,fma")

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
  TreeNode* increasingBST(TreeNode* root) {
    TreeNode* dummy = new TreeNode();
    TreeNode* current = dummy;
    dfs(root, current);

    current = dummy->right;
    delete dummy;

    return current;
  }

private:
  void dfs(TreeNode* node, TreeNode*& current) {
    if (node == nullptr) {
      return;
    }

    dfs(node->left, current);

    current->right = new TreeNode(node->val);
    current = current->right;

    dfs(node->right, current);
  }
};
```
