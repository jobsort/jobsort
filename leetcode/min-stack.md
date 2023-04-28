# Min Stack Problem & Solution

Design a stack that supports push, pop, top, and retrieving the minimum element in constant time.

Implement the `MinStack` class:

- `MinStack()` initializes the stack object.
- `void push(val)` pushes the element val onto the stack.
- `void pop()` removes the element on the top of the stack.
- `int top()` gets the top element of the stack.
- `int getMin()` retrieves the minimum element in the stack.

See the [min stack problem on LeetCode](https://leetcode.com/problems/min-stack).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack* obj = new MinStack();
 * obj->push(val);
 * obj->pop();
 * int param_3 = obj->top();
 * int param_4 = obj->getMin();
 */
class MinStack {
public:
  MinStack() {
    // noop
  }

  void push(int val) {
    tuple node = {val, val};

    // If we're pushing the first node, then the minimum is the value itself, but
    // otherwise, we need to calculate the running minimum.
    if (nums.size() > 0) {
      node.min = min(node.min, getMin());
    }

    nums.push_back(node);
  }

  void pop() {
    nums.erase(nums.end() - 1);
  }

  int top() {
    return nums[nums.size() - 1].val;
  }

  int getMin() {
    return nums[nums.size() - 1].min;
  }

private:
  struct tuple {
    int val;
    int min;
  };

  vector<tuple> nums;
};
```
