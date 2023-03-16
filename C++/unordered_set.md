# C++ unordered_set

## 基本用法

### 头文件

```c++
#include <unordered_set>
```

### 声明

```c++
unordered_set<int> mySet;
```

### 增

```c++
mySet.insert(1);
```

### 查

```c++
auto iter = mySet.find(1);
if (iter != mySet.end()) {
    cout << "Found: " << *iter << endl;
} else {
    cout << "Not found." << endl;
}
```

### 改

不能直接修改元素的值，因为unordered_set中每个元素是唯一的，需要先删除该元素，再插入一个新元素。

### 删

```c++
mySet.erase(1);
```

### 遍历

#### 使用迭代器遍历：

```c++
for (auto iter = mySet.begin(); iter != mySet.end(); ++iter) {
    cout << "Value: " << *iter << endl;
}
```

#### 使用for循环遍历：

```c++
for (const auto& elem : mySet) {
    cout << "Value: " << elem << endl;
}
```





