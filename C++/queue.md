# C++ queue

## 基本用法

### 头文件

```c++
#include <queue>
```

### 声明

```c++
queue<int> myQueue;
```

### 增

```c++
myQueue.push(42);
```

### 查

可以使用`front()`方法获取队列中第一个元素。

```c++
int firstElement = myQueue.front();
```

### 改

队列是一种先进先出的数据结构，不能像数组一样修改其中的元素。如果需要修改元素，则需要先将其删除，然后再将新元素添加到队列中。

### 删

使用`pop()`方法删除队列的第一个元素。

```c++
myQueue.pop();
```

### 遍历


#### 使用循环遍历：

```c++
while (!myQueue.empty()) {
    int currentElement = myQueue.front();
    // 对当前元素进行操作
    myQueue.pop();
}
```





