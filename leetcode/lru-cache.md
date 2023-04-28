# LRU Cache Problem & Solution

See the [LRU cache problem on LeetCode](https://leetcode.com/problems/lru-cache).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class LRUCache {
public:
  LRUCache(int capacity) {
    this->capacity = capacity;
  }
  
  int get(int key) {
    auto node = hash.find(key);
    if (node != hash.end()) {
      ll.splice(ll.begin(), ll, node->second.second);

      return (node->second).first;
    }

    return -1;
  }
  
  void put(int key, int value) {
    auto node = hash.find(key);
    if (node == hash.end()) {
      auto it = ll.insert(ll.begin(), key);

      hash.insert({key, {value, it}});
    } else {
      hash[key].first = value;

      ll.splice(ll.begin(), ll, node->second.second);
    }

    if (ll.size() > capacity) {
      auto it = prev(ll.end());
      int last_key = *it;

      ll.erase(it);
      hash.erase(last_key);
    }
  }

private:
  int capacity;
  list<int> ll;
  unordered_map<int, pair<int, list<int>::iterator>> hash;
};
```
