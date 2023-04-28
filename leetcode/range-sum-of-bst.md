# Range Sum of BST Problem & Solution

Given the `root` node of a binary search tree and two integers `low` and `high`, return the sum of values of all nodes with a value in the inclusive range `[low, high]`.

See the [range sum of BST problem on LeetCode](https://leetcode.com/problems/range-sum-of-bst).

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
  int rangeSumBST(TreeNode* root, int low, int high) {
    if (root == nullptr) {
      return 0;
    }

    int sum = 0;
    if (root->val >= low && root->val <= high) {
      sum += root->val;
    }

    if (root->val > low) {
      sum += rangeSumBST(root->left, low, high);
    }

    if (root->val <= high) {
      sum += rangeSumBST(root->right, low, high);
    }

    return sum;
  }
};
```
