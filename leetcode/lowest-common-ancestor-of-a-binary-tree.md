# Lowest Common Ancestor of a Binary Tree Problem & Solution

See the [lowest common ancestor of a binary tree problem on LeetCode](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree).

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
 *   TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
  TreeNode* lowestCommonAncestor(TreeNode* root, TreeNode* p, TreeNode* q) {
    vector<TreeNode*> ppath, qpath;

    help(root, p, ppath);
    help(root, q, qpath);

    TreeNode* result = root;
    for (int i = ppath.size() - 1, j = qpath.size() - 1; i >= 0 && j >= 0; --i, --j) {
      if (ppath[i] == qpath[j]) {
        result = ppath[i];
      } else {
        break;
      }
    }

    return result;
  }

private:
  bool help(TreeNode* root, TreeNode* needle, vector<TreeNode*>& path) {
    if (root == nullptr) {
      return false;
    }

    if (root == needle) {
      path.push_back(root);
      return true;
    }

    auto left = help(root->left, needle, path);
    auto right = help(root->right, needle, path);

    if (left || right) {
      path.push_back(root);
    }

    return left || right;
  }
};
```
