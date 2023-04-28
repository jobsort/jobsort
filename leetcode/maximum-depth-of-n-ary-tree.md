---
name: "Maximum Depth of N-ary Tree"
title: "LeetCode Maximum Depth of N-ary Tree Solution"
description: "Solution for given a n-ary tree, find its maximum depth. The maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node."
published: "2021-08-02 PDT"
modified: "2021-08-02 PDT"
---

# Maximum Depth of N-ary Tree Problem & Solution

Given a n-ary tree, find its maximum depth.

The maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

See the [maximum depth of n-ary tree problem on LeetCode](https://leetcode.com/problems/maximum-depth-of-n-ary-tree).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC optimization("max-inline-insns-recursive-auto")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

/*
class Node {
public:
  int val;
  vector<Node*> children;

  Node() {}

  Node(int _val) {
    val = _val;
  }

  Node(int _val, vector<Node*> _children) {
    val = _val;
    children = _children;
  }
};
*/
class Solution {
public:
  int maxDepth(Node* root) {
    if (root == nullptr) {
      return 0;
    }

    int depth = 0;
    for (int i = 0; i < root->children.size(); ++i) {
      depth = max(depth, maxDepth(root->children[i]));
    }

    return depth + 1;
  }
};
```
