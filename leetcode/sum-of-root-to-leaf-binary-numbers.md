---
name: "Sum of Root to Leaf Binary Numbers"
title: "LeetCode Sum of Root to Leaf Binary Numbers Solution"
description: "Solution for the sum of root to leaf binary numbers problem from LeetCode."
published: "2022-12-27 PDT"
modified: "2022-12-27 PDT"
---

# Sum of Root to Leaf Binary Numbers Problem & Solution

See the [sum of root to leaf binary numbers problem on LeetCode](https://leetcode.com/problems/sum-of-root-to-leaf-binary-numbers).

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
  int sumRootToLeaf(TreeNode* root) {
    vector<int> bits;

    return sumRootToLeaf(root, bits);
  }

private:
  int sumRootToLeaf(TreeNode* root, vector<int>& bits) {
    if (root == nullptr) {
      return 0;
    }

    if (root->left == nullptr && root->right == nullptr) {
      bits.push_back(root->val);

      int base10 = 0;
      for (int i = bits.size() - 1, j = 1; i >= 0; --i, j *= 2) {
        base10 += bits[i] * j;
      }

      bits.pop_back();

      return base10;
    }

    bits.push_back(root->val);
    int sum = sumRootToLeaf(root->left, bits) +
      sumRootToLeaf(root->right, bits);
    bits.pop_back();

    return sum;
  }
};
```
