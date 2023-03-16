# C++ unordered_map

## 基本用法

### 头文件

```c++
#include <unordered_map>
```

### 声明

```c++
unordered_map<int, int> myMap;
```

### 增

```c++
// 使用insert()函数
myMap.insert(make_pair(1, 10));

// 使用[]运算符
myMap[3] = 30;
```

### 查

```c++
auto iter = mymap.find(1);
if (iter != mymap.end()) {
    cout << "Found: " << iter->second << endl;
} else {
    cout << "Not found." << endl;
}
```

### 改

```c++
mymap[1] = 100;
```



### 删

```c++
myMap.erase(1);
```

### 遍历

#### 使用迭代器遍历：

```c++
for (auto iter = mymap.begin(); iter != mymap.end(); ++iter) {
    cout << "Key: " << iter->first << ", Value: " << iter->second << endl;
}
```

#### 使用for循环遍历：

```c++
for (const auto& elem : mymap) {
    cout << "Key: " << elem.first << ", Value: " << elem.second << endl;
}
```





