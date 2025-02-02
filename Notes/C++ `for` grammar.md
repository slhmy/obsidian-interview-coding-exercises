---
tags:
  - grammar/cpp
date: 2025-02-02
---
Usually we iterate through a range of values in the syntax of:

```cpp
for (auto it = arr.begin(); it != arr.end(); it++) {
    std::cout << *it << std::endl;
}
```

After C++11, we can use the range-based for loop to simplify the syntax:

```cpp
for (auto& val : arr) {
    std::cout << val << std::endl;
}
```
