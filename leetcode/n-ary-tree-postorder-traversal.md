# N-ary Tree Postorder Traversal Traversal Problem & Solution

Given the `root` of an n-ary tree, return the postorder traversal of its nodes' values.

N-ary tree input serialization is represented in their level order traversal.
Each group of children is separated by the null value.

See the [n-ary tree postorder traversal problem on LeetCode](https://leetcode.com/problems/n-ary-tree-postorder-traversal).

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
  vector<int> postorder(Node* root) {
    vector<int> traversal;

    postorder(root, traversal);

    return traversal;
  }

private:
  void postorder(Node* node, vector<int>& traversal) {
    if (node == nullptr) {
      return;
    }

    for (int i = 0; i < node->children.size(); ++i) {
      postorder(node->children[i], traversal);
    }

    traversal.push_back(node->val);
  }
};
```
