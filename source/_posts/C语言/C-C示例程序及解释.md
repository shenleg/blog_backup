---
title: C-C示例程序及解释
categories:
  - 编程语言
  - C
tags:
  - C
date: 2023-05-25 12:35:41
---

# 示例程序

```c
#include <stdio.h>

int main(void) {  // C 标准写法
  int num;  // 定义一个变量
  num = 1;  /* 为变量赋值 */
  
  printf("I am a simple computer\n");  // 调用函数
  printf("My favorite number is %d", num);
  
  return 0;
}
```

输出：

```
I am a simple computer
My favorite number is 1
```

# 解释

`#include <stdio.h>`：头文件

* 该行告诉编译器把 stdio.h 中的内容包含在当前程序中。
* stdio.h 是 C 编译器软件包的标准部分，它提供键盘输入和屏幕输出的支持。

`int main(void) {}`：函数

* 所有的 C 程序一定从 `main()` 函数开始执行，`main()` 函数约定俗成放在第一位。
* `int` 定义了函数的返回值、`main` 定义函数名、`(void)` 定义参数值（void 表示没有任何参数）、`{}` 定义函数体。

`int num;`：声明一个类型为 int，名为 num 的变量。

* 为变量在内存中分配存储空间，将变量与内存空间对应，确定**位置信息**和**空间大小**（类型作用）。
* **所有变量必须声明再使用**。
* 可以用大小写字母、数字、下划线来命名，第一个字符不能是数字。

`num = 1;`：把值 1 赋给变量 num。

`printf("I am a simple computer\n");`：调用函数

`return 0;`：返回值

* 给调用方返回值，这里给操作系统返回。



