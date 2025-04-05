  # Principle

Every index of the array saves the sum of the leaf nodes in the subtree.
When updating a leaf, all its parent nodes are updated;
When querying, find the position and all visible root nodes to its left, and then sum them up.
Therefore, both update and query have a time complexity of $O(\log n)$.

In the implementation code of the Binary Indexed Tree,
we use **LowBit** (check [[Bit Operation#Magic Usage]]) to quickly locate the node to be updated/summed.

# Code Implementation

```cpp
int treeArray[N];

// `x & (-x)` is a magic which helps you to
// get the lowest `1` bit of `x`
inline int lowBit(int x) { return x & (-x); }

void add(int i, int val) {
    while (i <= N) {
        treeArray[i - 1] += val; // 0-based index
        i += lowBit(i);
    }
}

int getSum(int i) {
    int sum = 0;
    while (i > 0) {
        sum += treeArray[i - 1]; // 0-based index
        i -= lowBit(i);
    }
    return sum;
}
```