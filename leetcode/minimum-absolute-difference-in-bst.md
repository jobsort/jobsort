# Minimum Absolute Difference in BST Problem & Solution

Given the `root` of a Binary Search Tree (BST), return the minimum absolute difference between the values of any two different nodes in the tree.

See the [minimum absolute difference in BST problem on LeetCode](https://leetcode.com/problems/minimum-absolute-difference-in-bst).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
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
  int getMinimumDifference(TreeNode* root) {
    vector<int> traversal;
    traverse(root, traversal);

    int diff = numeric_limits<int>::max();
    for (int i = 1; i < traversal.size(); ++i) {

      // Doing a diff between consecutive elements because they're sorted.
      diff = min(diff, abs(traversal[i - 1] - traversal[i]));
    }

    return diff;
  }

private:
  void traverse(TreeNode* root, vector<int>& traversal) {
    if (root == nullptr) {
      return;
    }

    // When traversing in-order, the nodes of a BST are sorted.
    traverse(root->left, traversal);
    traversal.push_back(root->val);
    traverse(root->right, traversal);
  }
};
```
