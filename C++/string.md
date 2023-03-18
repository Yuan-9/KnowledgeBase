# C++ string

## 基本用法

### 头文件

```c++
#include <string>
```

### 声明

```c++
string myString;
string myString = "Hello, World!";
```

### 增

```c++
myString += " This is a new sentence.";
// 或者
myString.append(" This is another new sentence.");
```

### 查

```c++
auto iter = myMap.find(1);
if (iter != myMap.end()) {
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
myString.erase(5, 7); // 从索引5开始，删除7个字符
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

## 其它函数

### 查询大小

```c++
size_t stringSize = myString.size();
// 或者
size_t stringLength = myString.length();
```

### 转换为其它数据类型

```c++
//转为int
int intValue = stoi(numberString);
//转为long
long longValue = stol(numberString);
//转为long long
long long longLongValue = stoll(numberString);
//转为float
float floatValue = stof(numberString);
//转为double
double doubleValue = stod(numberString);
//转为long double
long double longDoubleValue = stold(numberString);
```





