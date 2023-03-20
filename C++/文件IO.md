# C++ 文件IO

## 基本用法

### 头文件

```c++
#include <fstream>
```

### 示例

```c++
#include <iostream>
#include <fstream>
#include <string>

using namespace std;

int main() {
    // 打开输入文件
    ifstream input_file("input.txt");
    if (!input_file) {
        cerr << "无法打开输入文件" << endl;
        return 1;
    }

    // 打开输出文件
    ofstream output_file("output.txt");
    if (!output_file) {
        cerr << "无法打开输出文件" << endl;
        return 1;
    }

    // 从输入文件读取数据并写入输出文件
    string line;
    while (getline(input_file, line)) {
        output_file << line << endl;
    }

    // 关闭文件
    input_file.close();
    output_file.close();

    cout << "文件处理完成" << endl;
    return 0;
}
```



