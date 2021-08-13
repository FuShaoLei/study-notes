# C++快速入门

## 第一个C++程序

```c++
#include <iostream> // 引入头文件
using namespace std; //使用std的命名空间
int main() { // 主函数，所有程序的入口
    cout << "Hello, World!"; // 输出
    return 0;
}
```

## 基本数据类型

| 类型    | 说明     | 大小     |
| ------- | -------- | -------- |
| bool    | 布尔类型 |          |
| char    | 字符型   | 1字节    |
| int     | 整型     | 4字节    |
| float   | 浮点型   | 4字节    |
| double  | 双浮点型 | 8字节    |
| void    | 无类型   | 无       |
| wchar_t | 宽字符型 | 2或4字节 |

## 变量

```c++
int a; // 变量的声明
int b = 4; // 变量声明并初始化
```

##  函数

```c++
int max(int a, int b); // 声明
int max(int a, int b) { // 定义
    return a > b ? a : b;
}
```

这里跟c一样，必须在使用之前声明或者定义好，否则用不了！
