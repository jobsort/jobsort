---
name: "Convert Sorted Array to Binary Search Tree"
title: "LeetCode Convert Sorted Array to Binary Search Tree Solution"
description: "Solution for given an integer array nums where the elements are sorted in ascending order, convert it to a height-balanced binary search tree. A height-balanced binary tree is a binary tree in which the depth of the two subtrees of every node never differs by more than one."
published: "2021-08-25 PDT"
modified: "2021-08-25 PDT"
---

# Convert Sorted Array to Binary Search Tree Problem & Solution

Given an integer array `nums` where the elements are sorted in ascending order, convert it to a height-balanced binary search tree.

A height-balanced binary tree is a binary tree in which the depth of the two subtrees of every node never differs by more than one.

See the [convert sorted array to binary search tree problem on LeetCode](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimizations("max-inline-insns-recursive-auto")

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
  TreeNode* sortedArrayToBST(vector<int>& nums) {
    TreeNode* root = nullptr;
    sortedArrayToBST(nums, 0, nums.size() - 1, &root);

    return root;
  }

private:
  void sortedArrayToBST(vector<int>& nums, int low, int high, TreeNode** node) {
    if (low > high) {
      return;
    }

    int mid = low + (high - low) / 2;
    *node = new TreeNode(nums[mid]);
    sortedArrayToBST(nums, low, mid - 1, &(*node)->left);
    sortedArrayToBST(nums, mid + 1, high, &(*node)->right);
  }
};
```
