# Sum of Left Leaves Problem & Solution

Given the `root` of a binary tree, return the sum of all left leaves.

See the [sum of left leaves problem on LeetCode](https://leetcode.com/problems/sum-of-left-leaves).

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
  int sumOfLeftLeaves(TreeNode* root) {
    if (root == nullptr) {
      return 0;
    }

    int sum = 0;
    if (root->left != nullptr &&
        root->left->left == nullptr && root->left->right == nullptr) {
      sum += root->left->val;
    }

    return sum + sumOfLeftLeaves(root->left) + sumOfLeftLeaves(root->right);
  }
};
```
