# Construct String from Binary Tree Problem & Solution

See the [construct string from binary tree problem on LeetCode](https://leetcode.com/problems/construct-string-from-binary-tree).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("max-inline-insns-recursive-auto")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

/**
 * Definition for a binary tree node.
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
  string tree2str(TreeNode* root) {
    string s;
    tree2str(root, s);

    return s;
  }

private:
  void tree2str(TreeNode* root, string& s) {
    if (root == nullptr) {
      return;
    }

    s += to_string(root->val);
    if (root->left != nullptr) {
      s += "(";
      tree2str(root->left, s);
      s += ")";
    }

    if (root->left == nullptr && root->right != nullptr) {
      s += "()";
    }

    if (root->right != nullptr) {
      s += "(";
      tree2str(root->right, s);
      s += ")";
    }
  }
};
```
