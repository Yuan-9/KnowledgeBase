# C++ priority_queue

## 基本用法

### 头文件

```c++
#include <queue>
```

### 声明

```c++
priority_queue<int> pq;
```

#### 自定义比较

##### 使用库函数

默认情况下，`std::priority_queue`使用`std::less`作为比较函数，这意味着元素按降序排列，最大值具有最高优先级。要实现自定义优先级顺序，可以在声明优先队列时提供自定义比较函数。例如，要实现升序优先级队列，可以使用`std::greater`比较函数：

```c++
priority_queue<int, vector<int>, greater<int>> min_pq;
```

##### 自定义比较类

```c++
// 自定义比较类
class Compare {
public:
    bool operator()(const int& a, const int& b) const {
        // 自定义比较逻辑，例如：a % 10 与 b % 10 的比较
        return a % 10 > b % 10;
    }
};

int main() {
    priority_queue<int, vector<int>, Compare> pq;

}
```

##### lambda表达式

```c++
int main() {
    auto compare = [](const int& a, const int& b) { return a % 10 > b % 10; };
    using IntQueue = priority_queue<int, vector<int>, decltype(compare)>;

    IntQueue pq(compare);

}
```

`using`是C++关键字，用于定义类型别名。

`decltype`是C++11引入的关键字，用于查询表达式的类型。它在编译时确定表达式的类型，并可以将其用作类型别名或模板参数。`decltype`的一个典型用途是为模板推导出正确的类型。

### 增

```c++
pq.push(1);
```

### 查

优先队列不支持直接查找。要在优先队列中查找元素，可以将其底层容器导出为一个有序集合，然后对集合执行标准查找操作。

### 改

优先队列不支持直接修改元素。若要修改元素，通常的做法是先将元素从优先队列中删除，然后修改该元素，最后将修改后的元素重新插入到优先队列中。

### 删

要删除优先级最高的元素，可以使用`pop()`函数。注意`pop()`函数不会返回被删除的元素。要获取被删除的元素，需要在调用`pop()`之前使用`top()`函数。

```c++
pq.pop();
```

### 遍历

优先队列不提供遍历其元素的功能，因为其内部实现通常不保证完全排序。如果需要遍历优先队列中的元素，可以将优先队列的副本导出为一个排序后的集合，然后遍历该集合。需要注意的是，在这种情况下，原优先队列中的元素将被删除，因此需要操作副本以保留原始数据。

## 其它用法

### 判断优先队列是否为空

```c++
bool is_empty = pq.empty();
```

### 获取优先队列的大小

```c++
size_t num_elements = pq.size();
```

### 访问顶部元素

```c++
int highest_priority_element = pq.top();
```





