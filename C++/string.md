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
size_t pos = myString.find("world");
if (pos != string::npos) {
    cout << "Found at position: " << pos << endl;
} else {
    cout << "Not found" << endl;
}
```

### 改

```c++
//insert()：在指定位置插入子串。
myString.insert(5, " beautiful");
//replace()：替换指定位置开始的一定数量的字符为另一个字符串。
myString.replace(6, 9, "wonderful");
```

### 删

```c++
myString.erase(5, 7); // 从索引5开始，删除7个字符
```

### 遍历

#### 使用迭代器遍历：

```c++
for (auto it = myString.begin(); it != myString.end(); ++it) {
    cout << *it << endl;
}
```

#### 使用for循环遍历：

```c++
for (char c : myString) {
    cout << c << endl;
}
```

#### 使用下标遍历：

```c++
for (size_t i = 0; i < myString.length(); ++i) {
    cout << myString[i] << endl;
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





