# C++ lambda表达式

## 概述

`lambda`表达式（也称为匿名函数或lambda函数）是C++11及更高版本中引入的一种编程特性。它允许您在代码中创建一个简洁的、临时的、未命名的函数对象。Lambda表达式常用于简化那些需要将函数作为参数的场景，如`std::sort()`、`std::for_each()`等算法。

### 语法

Lambda表达式的一般语法如下：

```c++
[capture](parameters) -> return_type { function_body }
```

- `capture`：捕获列表，用于指定在lambda表达式内部要捕获的外部变量。可以使用`[]`表示空捕获列表，`[=]`表示值捕获所有变量，`[&]`表示引用捕获所有变量，或者明确指定捕获哪些变量。
- `parameters`：参数列表，与普通函数的参数列表类似。如果没有参数，可以省略括号。
- `return_type`：可选的返回类型。如果编译器可以自动推导返回类型，则可以省略。
- `function_body`：函数体，包含在大括号内。

### 示例

以下是一个简单的lambda表达式示例：

```c++
auto add = [](int a, int b) { return a + b; };

int sum = add(3, 5); // sum = 8
```

## 详细说明

### 捕获列表

1. 捕获列表是lambda表达式的一部分，用于指定哪些在lambda表达式外部定义的变量可以在lambda表达式内部使用。捕获列表使得lambda表达式可以访问并操作它们的上下文中的变量，这对于编写简洁的内联代码非常有用。捕获列表位于lambda表达式的开头，用方括号`[]`括起来。

	以下是捕获列表的几种形式：

	1. 空捕获列表（`[]`）：表示lambda表达式不捕获任何外部变量。

	```c++
	auto say_hello = []() { cout << "Hello, world!" << endl; };
	say_hello();  // 输出：Hello, world!
	```

	2. 值捕获（`[=]`）：表示lambda表达式以值方式捕获所有外部变量。这意味着在lambda内部，捕获的变量是它们在创建lambda时的副本。

	```c++
	int x = 10;
	auto add_x = [=](int a) { return a + x; };
	int result = add_x(5); // result = 15，x的值被捕获并加到5上
	```

	3. 引用捕获（`[&]`）：表示lambda表达式以引用方式捕获所有外部变量。这意味着在lambda内部，捕获的变量实际上是对它们的引用，您可以修改它们的值。

	```c++
	int x = 10;
	auto increment_x = [&]() { x++; };
	increment_x(); // x现在等于11
	```

	4. 混合捕获：表示lambda表达式以不同的方式捕获不同的外部变量。您可以为每个变量指定是按值捕获还是按引用捕获。

	```c++
	int x = 10;
	int y = 20;
	auto add_and_increment = [=, &y](int a) { y++; return a + x + y; };
	int result = add_and_increment(5); // result = 36, y现在等于21
	```

	在这个例子中，`x`以值方式被捕获，而`y`以引用方式被捕获。因此，在lambda内部，`x`的值保持不变，而`y`的值递增。

	通过使用捕获列表，您可以根据需要控制lambda表达式内部对外部变量的访问和修改。