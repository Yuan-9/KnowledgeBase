# C++ deque

## 基本用法

### 头文件

```c++
#include <deque>
```

### 声明

```c++
deque<int> myDeque;
```

### 增

使用`push_back()`方法向队列的末尾添加一个元素，使用`push_front()`方法向队列的头部添加一个元素。

```c++
myDeque.push_back(42);
myDeque.push_front(10);
```

### 查

可以使用`front()`方法获取队列的第一个元素，使用`back()`方法获取队列的最后一个元素。

```c++
int firstElement = myDeque.front();
int lastElement = myDeque.back();
```

### 改

双端队列可以通过下标访问和修改元素，也可以使用`at()`方法访问和修改元素。

```c++
myDeque[0] = 100;       // 修改第一个元素
myDeque.at(1) = 200;    // 修改第二个元素
```

### 删

使用`pop_back()`方法删除队列的最后一个元素，使用`pop_front()`方法删除队列的第一个元素。

```c++
myDeque.pop_back();
myDeque.pop_front();
```

### 遍历

#### 使用迭代器遍历：

```c++
for (auto it = myDeque.begin(); it != myDeque.end(); ++it) {
    int currentElement = *it;
    // 对当前元素进行操作
}
```