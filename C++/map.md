# C++ map

## 基本用法

### 头文件

```c++
#include <set>
```

### 声明

```c++
set<int> mySet;
```

#### 自定义比较

```c++
struct MyClass {
  int value;
};

bool cmp(const MyClass& a, const MyClass& b) {
  return a.value < b.value;
}

std::set<MyClass, decltype(&cmp)> mySet(&cmp);
```

### 增

```c++
mySet.insert(1);
```

时间复杂度为O(log n)

### 查

```c++
if (mySet.find(2) != mySet.end()) {
	std::cout << "2 is in the set\n" << endl;
}
```

时间复杂度为O(log n)

### 改

由于set中的元素是唯一的，因此不能直接修改一个元素。要修改一个元素，必须先删除该元素，然后再插入一个新元素。

### 删

```c++
mySet.erase(1);
```

时间复杂度为O(log n)

### 遍历

#### 使用迭代器遍历：

```c++
std::set<int>::iterator it;
for (it = mySet.begin(); it != mySet.end(); ++it) {
  std::cout << *it << " " << endl;
}
```

#### 使用for循环遍历：

```c++
for (const auto& elem : mySet) {
  std::cout << elem << " " << endl;
}
```





