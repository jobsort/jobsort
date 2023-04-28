# Kth Smallest Element in a BST Problem & Solution

See the [kth smallest element in a BST problem on LeetCode](https://leetcode.com/problems/kth-smallest-element-in-a-bst).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

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
  int kthSmallest(TreeNode* root, int k) {
    int i = 0, kth = -1;
    help(root, k, i, kth);

    return kth;
  }

private:
  void help(TreeNode* root, int k, int& i, int& kth) {
    if (root == nullptr || kth >= 0) {
      return;
    }

    help(root->left, k, i, kth);

    if (++i == k) {
      kth = root->val;
    }

    help(root->right, k, i, kth);
  }
};
```
