# Leaf-Similar Trees Problem & Solution

Consider all the leaves of a binary tree, from left to right order, the values of those leaves form a leaf value sequence.

Two binary trees are considered leaf-similar if their leaf value sequence is the same.

Return `true` if and only if the two given trees with head nodes `root1` and `root2` are leaf-similar.

See the [leaf-similar trees problem on LeetCode](https://leetcode.com/problems/leaf-similar-trees).

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
  bool leafSimilar(TreeNode* root1, TreeNode* root2) {
    vector<int> leaves1;
    vector<int> leaves2;

    dfs(root1, leaves1);
    dfs(root2, leaves2);

    return leaves1 == leaves2;
  }


private:
  void dfs(TreeNode* node, vector<int>& leaves) {
    if (node == nullptr) {
      return;
    }

    dfs(node->left, leaves);
    if (node->left == nullptr && node->right == nullptr) {
      leaves.push_back(node->val);
    }

    dfs(node->right, leaves);
  }
};
```
