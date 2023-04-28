# N-ary Tree Preorder Traversal Problem & Solution

Given the `root` of an n-ary tree, return the preorder traversal of its nodes' values.

N-ary tree input serialization is represented in their level order traversal.
Each group of children is separated by the null value.

See the [n-ary tree preorder traversal problem on LeetCode](https://leetcode.com/problems/n-ary-tree-preorder-traversal).

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
  vector<int> preorder(Node* root) {
    vector<int> traversal;

    preorder(root, traversal);

    return traversal;
  }

private:
  void preorder(Node* node, vector<int>& traversal) {
    if (node == nullptr) {
      return;
    }

    traversal.push_back(node->val);
    for (int i = 0; i < node->children.size(); ++i) {
      preorder(node->children[i], traversal);
    }
  }
};
```
