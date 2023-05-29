---
title: C-C Primer Plus 示例程序
categories:
  - 编程语言
  - C
tags:
  - C
date: 2023-05-25 12:35:41
---

# 第2章 C语言概述

## first.c

```c
// 示例程序
#include <stdio.h>

int main(void) {
    int num;  // 定义变量
    num = 1;  // 给变量赋值

    printf("I am a simple ");  // 调用函数，输出字符串
    printf("computer.\n");  // 输出占位符
    printf("My favorite number is %d because it is first. \n", num);  // 占位符输出 

    return 0;  // 返回值
}
```

输出：

```
I am a simple computer.
My favorite number is 1 because it is first. 
```



## fathm_ft.c

单位转换

```c
#include <stdio.h>

int main(void) {
    int feet, fathoms;
    fathoms = 2;
    feet = 6 * fathoms;

    printf("There ara %d feet in %d fathoms!\n", feet, fathoms);
    printf("Yes, I said %d feet!\n", 6 * fathoms);  // 待打印值可以是表达式

    return 0;
}
```

输出：

```
There ara 12 feet in 2 fathoms!
Yes, I said 12 feet!
```



## tow_func.c

包含多个函数

```c
#include <stdio.h>

void butler(void); // 声明函数原型，告知编译器要使用该函数

int main(void) {
    printf("I will summon the butler function.\n");
    butler();
    printf("Yes. Bring me some tea and writeable DVDs. \n");

    return 0;
}

// 开始定义函数
void butler(void) {
    printf("You rang, sir?\n");
}
```

输出：

```
I will summon the butler function.
You rang, sir?
Yes. Bring me some tea and writeable DVDs. 
```

## first.c

```c
#include <stdio.h>

int main(void) {
    int num;  // 定义变量
    num = 1;  // 给变量赋值

    printf("I am a simple ");  // 调用函数，输出字符串
    printf("computer.\n");  // 输出占位符
    printf("My favorite number is %d because it is first. \n", num);  // 占位符输出 

    return 0;  // 返回值
}
```

输出：

```
I am a simple computer.
My favorite number is 1 because it is first. 
```

## first.c

```c
#include <stdio.h>

int main(void) {
    int num;  // 定义变量
    num = 1;  // 给变量赋值

    printf("I am a simple ");  // 调用函数，输出字符串
    printf("computer.\n");  // 输出占位符
    printf("My favorite number is %d because it is first. \n", num);  // 占位符输出 

    return 0;  // 返回值
}
```

输出：

```
I am a simple computer.
My favorite number is 1 because it is first. 
```

## first.c

```c
#include <stdio.h>

int main(void) {
    int num;  // 定义变量
    num = 1;  // 给变量赋值

    printf("I am a simple ");  // 调用函数，输出字符串
    printf("computer.\n");  // 输出占位符
    printf("My favorite number is %d because it is first. \n", num);  // 占位符输出 

    return 0;  // 返回值
}
```

输出：

```
I am a simple computer.
My favorite number is 1 because it is first. 
```

