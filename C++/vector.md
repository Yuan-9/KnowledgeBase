# C++ vector

## 基本用法

### 头文件

```c++
#include <vector>
```

### 声明

```c++
vector<int> vec;
```

### 增

```c++
vec.push_back(1);
//insert()：在指定位置插入元素。
vec.insert(vec.begin() + 1, 3);
```

### 查

```c++
#include <algorithm>

int valueToFind = 3;
auto it = find(vec.begin(), vec.end(), valueToFind);

if (it != vec.end()) {
    cout << "Found " << valueToFind << " at position: " << distance(vec.begin(), it) << endl;
} else {
    cout << valueToFind << " not found in the vector." << endl;
}
```

### 改

`at()`函数在访问越界时会抛出`std::out_of_range`异常，而下标操作符不会进行边界检查。

```c++
vec[0] = 10;
vec.at(1) = 20;
```

### 删

```c++
vec.pop_back();
//erase()：删除指定位置的元素或一定范围内的元素。
vec.erase(vec.begin()); 
```

### 遍历

#### 使用迭代器遍历：

```c++
for (auto it = vec.begin(); it != vec.end(); ++it) {
    cout << *it << endl;
}
```

#### 使用for循环遍历：

```c++
for (int num : vec) {
    cout << num << endl;
}
```

#### 使用下标遍历：

```c++
for (size_t i = 0; i < vec.size(); ++i) {
    cout << vec[i] << endl;
}
```

## 其它用法

### 排序

默认情况下，排序为升序。

```c++
#include <algorithm>

sort(vec.begin(), vec.end());
```

#### 使用自定义比较函数进行自定义排序

要使用自定义比较函数进行排序，需要定义一个函数，该函数接受两个参数（要比较的元素）并返回一个布尔值。如果返回`true`，则表示第一个参数应该排在第二个参数之前；否则，相反。

```c++
// 自定义比较函数，降序排序
bool custom_compare(int a, int b) {
    return a > b;
}

int main() {
    vector<int> vec = {5, 3, 1, 4, 2};
    sort(vec.begin(), vec.end(), custom_compare);
    return 0;
}
```

#### 使用lambda表达式进行自定义排序

```c++
int main() {
    vector<int> vec = {5, 3, 1, 4, 2};
    sort(vec.begin(), vec.end(), [](int a, int b) { return a > b; });

    return 0;
}
```





